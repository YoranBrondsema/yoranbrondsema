---
title: "Do not pass records to your Rails mailers"
date: 2017-11-04T15:46:43-05:00
slug: "do-not-pass-records-to-your-rails-mailers"
tags: ["Computer things"]
---

## The problem
[Sutori](https://www.sutori.com) has a system of inviting users to your story.
As the author, you give the email of the invitee. In the backend, it then
creates a record of type `Invitation` and sends the invitation email. The mailer
looks like this:

```ruby
class InvitationMailer < ApplicationMailer
  def invitation(invitation:)
    mail(
      to: invitation.email,
      subject: "You've been invited!"
    )
  end
end
```

Then we started getting the following errors:

```ruby
ActiveJob::DeserializationError: Error while trying to deserialize arguments:
Couldn't find Invitation with 'id'=12345
```

The crucial part is that the email is sent asynchronously through ActiveJob.
This is the sequence of events that caused this error:

1. The user creates the invitation.
2. In the backend, the `Invitation` record is created and the email is added to
   the queue of background jobs.
3. The user deletes the invitation, maybe because he made a typo in the email
   addres.
4. The `Invitation` record is deleted from the database.
5. It was a busy period for the background jobs so the mail from step 2 is only
   now sent. Then when Rails tries to load the `Invitation` record from the
   database, it fails with the error above.

The consequences are not severe in the sense that the mail simply won't get sent
because of the exception. However, it's never a good thing to have preventable
exceptions in your log as it clutters it and removes the attention from real
exceptions. Therefore, it should be cleaned up. This is further aggravated by
the fact that some background processors, e.g.
[Sidekiq](https://github.com/mperham/sidekiq), retry a job multiple times before
it's killed. So this exception will show up multiple times for the same email.

## The solution
The solution is simple: instead of passing the full record to the mailer, we
only pass it an ID. We then abort if the record does not exist in the database.
So the mailer interface becomes:

```ruby
class InvitationMailer < ApplicationMailer
  def invitation(invitation_id:)
    invitation = Invitation.find_by(id: invitation_id)
    return if invitation.nil?

    mail(
      to: invitation.email,
      subject: "You've been invited!"
    )
  end
end
```

Thanks to [this PR](https://github.com/rails/rails/pull/8048) that was merged
into Rails back in 2012, the mail won't get rendered if no call to `mail()` is
made.

## Bottom line
The bottom line is that you can never assume the presence of records in
background jobs. Since they are processed asynchronously, the state of the
database will likely have changed by the time the job is processed.

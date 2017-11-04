+++
title = "yoranbrondsema.com v2.0"
date = 2017-11-02T19:37:17-05:00
tags = ["Meta"]
+++

Unfortunately I was too laxist with renewing the hosting that this website was
previously using. By the time I wanted to renew, it was too late and the entire
site had been deleted by the hosting provider, including the database. This
means that all the content that was on there was lost. This is a shame and I
take the blame for it. My only consolation is that a lot of the posts were
about Ember.js and Ruby on Rails development and therefore were more or less
outdated by now.

However, I take this as a chance to revamp the blog. It was previously powered
by Wordpress but in hindsight that was a bit overkill for a simple blog.
Instead, I now focused on simplicity and therefore chose to use
[Hugo](https://gohugo.io/), the static site generator. It's the first time that
I use a static site generator and we'll see how it plays out. However, it
already makes me happy that I can type this in my favorite editor Vim. It is a
little ironic though as during the day I work on
[Sutori](https://www.sutori.com), a full Javascript single-page application
built on Ember.js.

### Hosting
The domain name is registered via OVH.com for which I pay €7.99 per year. This
comes with 10 MB of free hosting so for now that is my only cost. We'll see
how long this will last me but it's also an incentive to keep things minimal.

### Deployment
The free hosting plan has its limitations so I can only deploy via FTP. This
takes me back to the days of when I made my first websites! Back in the day I
was dragging the files from [left to right](https://wiki.filezilla-project.org/wiki/images/0/06/Navigating-remote.png)
but now I know better luckily.

I am using [hugodeploy](https://github.com/mindok/hugodeploy) to deploy the
website to the FTP server. FTP is not a quick protocol so it's good that it
only uploads files that have changed in between deployments.

I keep the source of the blog on a [public GitHub repository](https://github.com/YoranBrondsema/yoranbrondsema)
so I perform a deployment after each Git push:

    # .git/hooks/pre-push

    hugo
    hugodeploy

### Conclusion
It's a shame the old blog was deleted but it's an opportunity to start afresh.
I'm already in love with the immediacy of a static site generator. I press
`:wq` on Vim and with only one command, the changes are live and deployed.

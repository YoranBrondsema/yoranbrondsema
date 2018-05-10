---
title: "What If I Lose My 2FA"
date: 2018-05-01T20:42:46-05:00
---

## Be prepared for the day you lose your phone

Last weekend I released a little side-project called
<a href="https://www.whatifilosemy2fa.com/">What If I Lose My 2FA</a>. The impetus
was the famous "Boot Loop of Death" that happened to my Nexus 5X a couple of
weeks ago. I got the phone fixed in the end but only after having to reinstall a
fresh version of Android.

That was not a huge issue except that I had secured many services with 2FA using
the Google Authenticator software token app. I was locked out of all those
services now. For some I had saved recovery codes which allowed me to get back
in, but unfortunately not for all.

And I can tell you that it was quite a hassle to regain access to those
accounts. Most notably, getting back into Sutori's AWS account required a visit
to the notary to sign and seal an affidavit.

Needless to say, this was an adventure I didn't want to put myself through a
second time. I vowed myself to be better prepared in case I lose access to my
phone again. A phone can get broken, lost or stolen so this will inevitably
happen.

One of the difficulties in being prepared is that each service handles the loss
of a 2FA device differently. For instance, you can get back into AWS with a
matching email address and phone number. On the other hand, Google hands out
single-use backup codes that you can use instead of a 2FA-generated code.

This is the reason that I created <a href="https://www.whatifilosemy2fa.com/">What If I Lose My 2FA</a>.
It gives exactly the information that you need to keep in order to recover your
account for a variety of services.

I hope it's of use to you! And don't hesitate to fill out the
<a href="https://yoranbrondsema.typeform.com/to/xd9LJ3">form to propose a service</a>
if there's one you'd like to see up there.

## Some technical specs
* The website is a single-page application built with Ember.js. It's most
  certainly overkill for this project but it's what I know best. Therefore I
  was able to build and deploy it in a couple of hours.
* It stores your choice of services in your browser's local storage. I didn't
  want to deal with a backend.
* It works offline thanks to service workers! This deserves a shoutout to the
  maintainers of the <a href="https://github.com/DockYard/ember-service-worker">ember-service-worker</a>
  addon.
* Deployed and hosted by Netlify. The Heroku-esque way of automatically
  deploying after a `git push origin master` is so easy. Setting up HTTPS is
  also a breeze. And it's free for static websites!

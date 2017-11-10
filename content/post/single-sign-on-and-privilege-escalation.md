---
title: "Single sign on and privilege escalation"
date: 2017-11-09T20:55:05-06:00
slug: 'single-sign-on-and-privilege-escalation'
tags: ['Security']
---

Over the past few years, it's become common to use your Google, Twitter, or even
Facebook account to sign up for other services. This speeds up the sign up
process as you don't need to fill in any sign up form, nor do you have to open
up your email client to click on the verification link before your can actually
use the service. It also removes the necessity to choose and remember yet
another password, although this is not as cumbersome anymore if you use a
password manager.

However, this convenience comes at the cost of greatly multiplying the
consequences of a hack. Indeed, say that you use your Twitter account to log
into 10 additional services. If your Twitter account gets hacked, the hacker
will not just have access to your Twitter account but also to those 10 services.

Therefore, it is even more crucial to secure these "foundational" accounts, i.e.
the accounts that you use to log into other services, with multi-factor
authentication. [2FA with SMS is insecure](https://www.schneier.com/blog/archives/2016/08/nist_is_no_long.html)
so you should use something like [Google Authenticator](https://en.wikipedia.org/wiki/Google_Authenticator)
that implements TOTP or HOTP.

---
title: "Move to Netlify"
date: 2017-11-30T18:35:50-06:00
slug: "move-to-netlify"
tags: ["Computer things"]
---

In <a href="{{< ref "post/yoranbrondsema-com-v2-0.md" >}}">a previous post</a> I
explained that I used a simple FTP server to deploy this blog. However, I have
since moved to <a href="https://www.netlify.com/">Netlify</a> after I heard
about it in a Hacker News thread. It offers the following advantages:

* It hooks into the repository on GitHub so every push to the `master` branch
  triggers a deploy. This removes the need for custom Git hooks and deploy
  scripts.
* It acts as a CDN so it should be quicker to load (I haven't measured this).
  Previously, it was hosted on a single server in France through OVH.
* It takes care of HTTPS certificate setup and renewal through the awesome <a
  href="https://letsencrypt.org/">Let's Encrypt</a> service.
* Most importantly, it <a href="https://www.netlify.com/pricing/">is free</a>
  for the features that I use. Let's hope it stays that way!

I have found no disadvantages except that I now rely on an external service to
deploy the blog.

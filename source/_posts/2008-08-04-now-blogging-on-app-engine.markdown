---
layout: post
comments: true
title: "Now blogging on App Engine"
date: 2008-08-04 00:00
categories: [django, blogging, python, App Engine, programming]
---

About a week ago, I wrote that [this blog is now running under Django][] on
a low-end [VPS][] I lease. Writing my own simple blogging engine was a
good, well-defined project I could use to acquaint myself with [Django][].

Over this weekend, I decided to rehost it on Google's [App Engine][].
Again, it's a well-defined project that I can use to learn more about how
App Engine works.

As it turns out, porting the application to App Engine wasn't
difficult.

- App Engine's database API is similar to Django's. It differs in
  the details, but the overall approach is quite similar.
- App Engine's default template engine is from Django, so I
  didn't have to change any of my templates.
- App Engine doesn't specifically use views in the way Django
  does. Instead,n you tie URLs to individual scripts that App Engine
  invokes. In practice, however, those scripts end up serving
  essentially the same role as a Django view.

In my first port, I simply ran Django underneath App Engine; App
Engine supports that configuration. However, while that got my blog
up and running quickly on App Engine, it didn't force me to dig
deeply into any part of App Engine other than its database API.

So, I spent a few hours converting the software to use App Engine's
webapp framework, rather than Django. As it turns out, it wasn't
terribly difficult. The biggest issue was that App Engine does not
provide automatic generation of administration screens, so I had to
write my own screens to enter and edit blog entries. All told,
however, it wasn't a big effort.

Later, I'll write one or more blog posts on writing a simple
blogging engine using App Engine.

[this blog is now running under Django]: /id/73/
[VPS]: http://onlinebusiness.about.com/od/webhosting/g/vps.htm
[Django]: http://www.djangoproject.com/
[App Engine]: http://appengine.google.com/

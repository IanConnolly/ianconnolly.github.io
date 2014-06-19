---
layout: post
title: 4 Weeks At Mozilla
description: My First 4 Weeks Interning at Mozilla
category: mozilla
---

I'm mid-way through my 4th week interning on Mozilla's Release Engineering team
in San Francisco. I'll save all of the _oh my god San Francisco_ and more
personal Mozilla-related flailing for another blog post - probably nearer to
when I'm headed home. But I wanted to begin making a stab at documenting
what I'm doing work-wise while I'm out here, in the spirit of
the Mozilla mission.

Briefly, for some background, Release Engineering are the team at Mozilla
who build the delivery pipeline that takes Mozilla products from our developers
and contributors and gets them out to our users. Continuous integration,
testing, building, and release infrastructure development + operations
and everything in between. Releng lets everybody else do more with less by
making everybody else more effective. How we do that and why it is so important
to helping Mozilla compete with far larger organisations is probably best
left to Mozilla's former Director of Release Engineering John O'Duinn
whose
[Release Engineering As A Force Multiplier](http://youtu.be/7j0NDGJVROI) talk
is the best thing you'll see this week.

I'll save the details of what getting up to speed meant for me in a specific
later post but let's just say that was a project all of its own for a couple of
weeks and a quick thank you to my mentor [Hal Wine](https://twitter.com/hwine)
is most definitely in order because he's been such a huge help.

My [first project](https://bugzilla.mozilla.org/show_bug.cgi?id=712206) was
writing a Puppet module for my colleague
[Chris AtLee](http://atlee.ca/blog/)'s project
[Runner](https://github.com/catlee/runner). Runner was built to help us manage
what happens pre-flight for our build &amp; test jobs on our
slaves. A huge amount of resources are wasted and complexity added &amp;
duplicated by having these checks inside our build and test jobs rather than
managed externally. More resources available means everything else runs faster,
smoother, and cheaper - making Mozilla that little bit more effective.
Runner v1.0 is being deployed this week, and all going well I should be
starting work on Runner N+1 next week.

Concurrently to this, I started a rebuild of
[Clobberer](https://wiki.mozilla.org/ReleaseEngineering/Applications/Clobberer).
A clobber is when we completely destroy an objdir on build slaves, and Clobberer
is our programmatic and web interface for doing this.
We wanted Clobberer to fit more easily into this new, Runner-oriented world
that we're creating. This meant a cleaner CLI interface, but also a more
robust backend API. Clobberer's backend had become an unwieldy mess of PHP that
obfuscated what we were actually doing. Even just doing a one-to-one rebuild
of it and splitting the logic out into a sanely constructed Flask application
while cutting all of the dead code will be a big win - so that's my plan for
v1.0. You can follow its progress
[here](https://github.com/IanConnolly/build-clobberer-app).

The new application is structured as a blueprint on the new
[Releng API](https://github.com/mozilla/build-relengapi) project which
[Dustin](http://code.v.igoro.us/) introduced
[yesterday](http://code.v.igoro.us/posts/2014/06/Introducing-Relengapi.html).
If you've ever spoken to me about development, you probably know that I
love a good HTTP API written in Flask, so I was super enthusiastic when I heard
about the project and am glad to be helping out. I'm also building out a
[template/example project](https://github.com/IanConnolly/build-relengapi-template)
to help other people structure and build more services on top of Releng API.
I was also able
to [make a PR](https://github.com/mozilla/build-relengapi/pull/85)
to something I don't 'own' responsibility for, which was a great feeling.

~4 weeks down, here's to 8 more great ones.

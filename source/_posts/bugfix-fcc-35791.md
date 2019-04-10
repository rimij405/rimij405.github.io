---
title: 'Squashing Bugs - freeCodeCamp Issue #35791 (PR #35792)'
tags:
  - bugfix
  - education
  - open-source
categories:
  - - blog
    - hfoss
  - freeCodeCamp
photos:
  - /images/posts/bugfix/fcc_banner2.png
date: 2019-04-08 01:14:25
---


# Squashing Bugs - freeCodeCamp Issue #35791 #

I was in the middle of responding to issue [#35751](https://github.com/freeCodeCamp/freeCodeCamp/issues/35751) for [freeCodeCamp](https://www.freecodecamp.org/), when I found a typo in the local development setup guides! I was writing up the other bugfix report as I churned along, but, wow - I managed to contribute and have my changes accepted for a completely different effort!

To note, this post is for issue `#35791` and **not** the very similarly numbered `#35751`, which I am in the middle of writing another bugfix report for. You'll see my other report on this site once I finish editing files and performing a spell-check. That draft is sitting on my harddrive, so, even if you end up seeing this first, this is my *second* magic trick.

But it's one that resulted in a successful pull request ([#35792](https://github.com/freeCodeCamp/freeCodeCamp/pull/35792)) as well!

![Logo for Free Code Camp.](/images/posts/bugfix/fcc_logo.svg)

The nonprofit's mission is simple: help *campers* learn to code. For free. (*And this time, it's free as in pizza **and** free as in libre*). I did a brief review on the Free Code Camp code base in preparation for the {% post_link bugfix-fcc-35751 other bugfix report here %}. {% post_link commarch-fcc You can read my FLOSS review post here. %}

<!-- Read more -->

## Overview ##

I was reading over the [local developer setup guide](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally.md) when I came across an innocuous typo. The link to the contributor's forum hadn't been updated!

![Screenshot of the suspect.](/images/posts/bugfix/fcc_bugfix-link.png)

## The Issue ##

Since I already had read the [contributor's guide](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/CONTRIBUTING.md). I was ready to roll. I went ahead and created a new issue ([#35791](https://github.com/freeCodeCamp/freeCodeCamp/issues/35791)). 

I gave information about steps on how to reproduce the error, what I believed the expected outcome should have been, and followed all of the contributor guidelines that they had set out for us.

## Squashing the Bug ##

Squashing this bug was simple: I had to change the links to point to the correct location.

## Creating a Pull Request ##

Once the pull request ([#35792](https://github.com/freeCodeCamp/freeCodeCamp/pull/35792)) was created, it passed the Travis CI build tests, and was accepted by one of the core maintainers for the repository.

![Screenshot of the issue showing the merged pull request.](/images/posts/bugfix/fcc_pull6.png)

The issue ([#35791](https://github.com/freeCodeCamp/freeCodeCamp/issues/35791).) thread also reflects that the pull request was accepted.

![Screenshot of the issue showing the merged pull request.](/images/posts/bugfix/fcc_pull5.png)

With that, my first pull request was accepted! All while I was trying to get {% post_link bugfix-fcc-35751 another bugfix %} done.
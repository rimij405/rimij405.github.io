---
title: 'Squashing Bugs - freeCodeCamp Issue #35751'
tags:
  - bugfix
  - education
  - open-source
categories:
  - - blog
    - hfoss
  - freeCodeCamp
photos:
  - /images/posts/bugfix/fcc_acknowledgements.png
date: 2019-04-05 01:14:25
---

# Squashing Bugs - freeCodeCamp Issue #35751 #

For my first magic trick:

![Logo for Free Code Camp.](/images/posts/bugfix/fcc_logo.svg)

I'm contributing to [freeCodeCamp](https://www.freecodecamp.org/) and helped make a pull request referencing issue [#35751](https://github.com/freeCodeCamp/freeCodeCamp/issues/35751). The nonprofit's mission is simple: help *campers* learn to code. For free. (*And this time, it's free as in pizza **and** free as in libre*). I hope by documenting my own process, members of the community might get to see an example of what it is that goes on behind the scenes. Before jumping in, I did a little bit of research on freeCodeCamp. {% post_link commarch-fcc You can read my FLOSS review post here. %}

<!-- Read more -->

## Overview ##

I'm started writing this post as soon as I [commented](https://github.com/freeCodeCamp/freeCodeCamp/issues/35751#issuecomment-480128455), volunteering to fix the outstanding issue and was quickly welcomed into the community!

My first step after volunteering was to read the [contributor's guide](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/CONTRIBUTING.md). After reviewing their [Code of Conduct](https://www.freecodecamp.org/code-of-conduct) and deciding that I'd want to work locally before submitting my changes, I hopped into their guides on [coding challenge](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-work-on-coding-challenges.md) and [local development](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally.md).

I was ready to roll. Now would be a good time to review what the issue actually was!

## The Issue ##

Issue [#35751](https://github.com/freeCodeCamp/freeCodeCamp/issues/35751) was posted about a day ago by Randell Dawson ([@RandellDawson](https://github.com/RandellDawson)) with the title: "Need to add full working solutions for over 100 challenges in the Responsive Web Design section."

I've copied the pertinent part of the initial post below for your convienience:

<!-- markdownlint-disable MD034 -->
{% blockquote Randell Dawson, freeCodeCamp https://github.com/freeCodeCamp/freeCodeCamp/issues/35751 Issue #35751 %}
<!-- markdownlint-enable MD034 -->

With a quick search, I found there are currently 104 challenges in the Responsive Web Design section that are missing a full working solution. I wan[t] to use this issue to help track who wants to work on adding these and when the PRs get merged.

{% endblockquote %}

Don't worry, I didn't have to make the solution for all **104** at once. I signed up to tackle the 16 challenges underneath `Applied Accessibility`. Seems simple enough, right?

This meant I needed to fix the following files:

- give-links-meaning-by-using-descriptive-link-text.english.md
- improve-accessibility-of-audio-content-with-the-audio-element.english.md
- improve-chart-accessibility-with-the-figure-element.english.md
- improve-form-field-accessibility-with-the-label-element.english.md
- improve-readability-with-high-contrast-text.english.md
- jump-straight-to-the-content-using-the-main-element.english.md
- know-when-alt-text-should-be-left-blank.english.md
- make-elements-only-visible-to-a-screen-reader-by-using-custom-css.english.md
- make-links-navigable-with-html-access-keys.english.md
- make-screen-reader-navigation-easier-with-the-footer-landmark.english.md
- make-screen-reader-navigation-easier-with-the-header-landmark.english.md
- make-screen-reader-navigation-easier-with-the-nav-landmark.english.md
- use-tabindex-to-add-keyboard-focus-to-an-element.english.md
- use-tabindex-to-specify-the-order-of-keyboard-focus-for-several-elements.english.md
- wrap-content-in-the-article-element.english.md
- wrap-radio-buttons-in-a-fieldset-element-for-better-accessibility.english.md

## Building the Local Environment ##

So far, one of the more frustrating development environments that I've had to set up. I really wish there was an easier way for the project to run on Windows 10 Home. That being said, you can read about my exploits here.

That long story is best told separately; but you should know that it compiled successfully and I was greeted with a working site:

![Screenshot of successful compilation process.](/images/posts/bugfix/fcc_triage_success.png)

## Solving the Challenges ##
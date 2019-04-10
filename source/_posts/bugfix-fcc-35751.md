---
title: 'Squashing Bugs - freeCodeCamp Issue #35751 (PR #35809, #35810)'
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
date: 2019-04-09 12:29:08
---

# Squashing Bugs - freeCodeCamp Issue #35751 #

For my first magic trick:

![Logo for Free Code Camp.](/images/posts/bugfix/fcc_logo.svg)

I'm contributing to [freeCodeCamp](https://www.freecodecamp.org/) and helped make two pull requests ([#35809](https://github.com/freeCodeCamp/freeCodeCamp/pull/35809), [#35810](https://github.com/freeCodeCamp/freeCodeCamp/pull/35810)) referencing this issue ([#35751](https://github.com/freeCodeCamp/freeCodeCamp/issues/35751)). The nonprofit's mission is simple: help *campers* learn to code. For free. (*And this time, it's free as in pizza **and** free as in libre*). I hope by documenting my own process, members of the community might get to see an example of what it is that goes on behind the scenes. Before jumping in, I did a little bit of research on freeCodeCamp. {% post_link commarch-fcc You can read my FLOSS review post here. %}

<!-- Read more -->

## Overview ##

I started writing this post as soon as I [commented](https://github.com/freeCodeCamp/freeCodeCamp/issues/35751#issuecomment-480128455), volunteering to fix the outstanding issue and was quickly welcomed into the community!

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

- [give-links-meaning-by-using-descriptive-link-text.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/give-links-meaning-by-using-descriptive-link-text.english.md)
- [improve-accessibility-of-audio-content-with-the-audio-element.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/improve-accessibility-of-audio-content-with-the-audio-element.english.md)
- [improve-chart-accessibility-with-the-figure-element.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/improve-chart-accessibility-with-the-figure-element.english.md)
- [improve-form-field-accessibility-with-the-label-element.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/improve-form-field-accessibility-with-the-label-element.english.md)
- [improve-readability-with-high-contrast-text.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/improve-readability-with-high-contrast-text.english.md)
- [jump-straight-to-the-content-using-the-main-element.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/jump-straight-to-the-content-using-the-main-element.english.md)
- [know-when-alt-text-should-be-left-blank.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/know-when-alt-text-should-be-left-blank.english.md)
- [make-elements-only-visible-to-a-screen-reader-by-using-custom-css.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/make-elements-only-visible-to-a-screen-reader-by-using-custom-css.english.md)
- [make-links-navigable-with-html-access-keys.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/make-links-navigable-with-html-access-keys.english.md)
- [make-screen-reader-navigation-easier-with-the-footer-landmark.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/make-screen-reader-navigation-easier-with-the-footer-landmark.english.md)
- [make-screen-reader-navigation-easier-with-the-header-landmark.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/make-screen-reader-navigation-easier-with-the-header-landmark.english.md)
- [make-screen-reader-navigation-easier-with-the-nav-landmark.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/make-screen-reader-navigation-easier-with-the-nav-landmark.english.md)
- [use-tabindex-to-add-keyboard-focus-to-an-element.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/use-tabindex-to-add-keyboard-focus-to-an-element.english.md)
- [use-tabindex-to-specify-the-order-of-keyboard-focus-for-several-elements.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/use-tabindex-to-specify-the-order-of-keyboard-focus-for-several-elements.english.md)
- [wrap-content-in-the-article-element.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/wrap-content-in-the-article-element.english.md)
- [wrap-radio-buttons-in-a-fieldset-element-for-better-accessibility.english.md](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/wrap-radio-buttons-in-a-fieldset-element-for-better-accessibility.english.md)

## Building the Local Environment ##

So far, one of the more frustrating development environments that I've had to set up. I really wish there was an easier way for the project to run on Windows 10 Home. That being said, you can read about my exploits here.

That long story is best told {% post_link triage-fcc-local-dev-setup separately %}; but you should know that it compiled successfully and I was greeted with a working site:

![Screenshot of successful compilation process.](/images/posts/bugfix/fcc_triage_success.png)

You can read the steps I took to get the environment ready for development {% post_link triage-fcc-local-dev-setup here %}.

Once the local development environment is ready, developers are encouraged to:

1. Seed the MongoDB instance with `npm run seed`.
2. Host the platform on a local server with `npm run develop`.
3. Perform all of the JS tests in the system `npm test`.

Once changes are made, there is even an interactive tool that can help with creating a proper commit message, with `npm run commit`.

## Reviewing the Challenges ##

As part of the broader 104 challenges missing full working solutions, the main issue itself has had the work divvied up between different contributors. The platform's curriculum is broken up into nine sections: six core courses, one section for interview prep, and one additional section for handling certificates. I've agreed to work on a sub-section of the first course, Responsive Web Design. My 16 challenges deal with the subject of 'Applied Accessibility'.

Of note, my work will only be addressing the issue in the core English translation of the challenges. As per the instructions of the current developers, they always track changes to the solutions through the English version of the challenges so that the translations can be updated without worrying about the core logic behind the code itself.

### Applied Accessibility ###

According to the curriculum's introduction on the topic, *accessibility*, "generally means having web content and a user interface that can be understood, navigated, and interacted with a broad audience." People of various ability use the internet - if your website contains layer upon layer of beautiful images, video, and audio, without containing the foundational elements that make it accessible, the potential audience that can utilize such a website shrinks.

There is something to be said about a developer's responsibility to keeping accessibility a priority - ensuring that a website is inclusive of users that require assitive technology is a crucial part in making sure the internet remains free and open. One could argue that inaccessible software, that cannot be run, read, repaired, or redistributed by everyone is not 100% open.

On January 18th, 2017, [the U.S. Federal Registry published the Revised Section 508 amendment to the Rehabilitation Act of 1973](https://opensource.com/article/17/3/applications-should-be-accessible-all). The new standards renewed encouragement for developers to create accessible web and mobile applications. [W3 Consortium's Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/) (WCAG) set the international standard for accessibility and provides a number of criteria for developers to use to check their work against.

The lessons under Applied Accessibility explore these general concepts:

1. Writing well-organized code that uses the appropriate markup.
2. Ensuring text alternatives exist for non-text and visual content.
3. Creating an easily-navigated page that's keyboard-friendly.

### Completing a Challenge ###

Taking a look at the first challenge in the provided list gives us ['Give Links Meaning by Using Descriptive Link Text'](https://learn.freecodecamp.org/responsive-web-design/applied-accessibility/give-links-meaning-by-using-descriptive-link-text).

![Screenshot of the first challenge being troubleshot.](/images/posts/bugfix/fcc_challenge1_problem.png)

The website itself has three sections:

1. The description of the prompt and interaction buttons. (On the left in the picture).
2. The starter code that the user needs to edit to submit and the output console. (In the middle).
3. The preview of the starter code.

In this particular challenge, the camper is expected to make the page more accessible. Free Code Camp accomplishes this by placing a specific, guided prompt for the user to accomplish. In this instance, the prompt asks users to move, "the anchor (`a`) tags so they wrap around the text "information about batteries" instead of "Click here". This improvement will allow users of screen readers to gleam more context from a page's link when the utilize functionality to read out a list of all the links on the page.

For each challenge, to familiarize myself with the issue at hand, I try solving the exercise myself. I change the anchor tag in the demo area so it reads as `<a href="">Click here for more information about batteries</a>`. This should fulfill the prompt, right?

![Screenshot of my first attempt to solve the exercise.](/images/posts/bugfix/fcc_challenge1_attempt1.png)

Wrong!

![Screenshot of my first failure in solving the exercise.](/images/posts/bugfix/fcc_challenge1_fail1.png)

Instead of passing, the test has failed because 'Click here' is still contained by the anchor tag. The platform gives back some helpful feedback for users who might be stuck solving a problem. If the test information doesn't make it clear enough, users can watch a video, ask for help, or get a hint in order to make progress. Campers can even start the process over by reseting all of the code back to the original state.

Now, I don't want to be wrong, so, I move the tag to the right place and submit once more.

![Screenshot of my first success in solving the exercise.](/images/posts/bugfix/fcc_challenge1_success1.png)

Seeing as all of the tests have passed, I'm greeted by a big, green checkmark. How fulfilling! If I can complete the challenge, what is it that I'll need to bugfix next!

### Forming a Challenge ###

It would help to know what makes a challenge and now is a good time to look under the hood to find out more about the problem we're trying to fix. Challenges aren't too complicated or difficult to understand: they're just markdown files (with some YAML syntax here and there). In fact, they're written in the same way *that my own blog posts are written*.

These six sections make up a challenge's markdown file:

1. The YAML header containing challenge metadata.
2. `Description` - The challenge's description.
3. `Instructions` - The prompt that explains the challenge users need to solve.
4. `Tests` - A fenced code block with a YAML list of assertions.
5. `Challenge Seed` - The starting code given that needs to be modified in order to solve.
6. `Solution` - The full solution required to solve the problem.

A challenge is identified by a unique ID, title, and challenge type - all of which are stored in the metadata section. As all challenges will ideally contain a link to a [Scrimba](https://scrimba.com/ "Platform for streamcasting code.") video, the metadata will often include a relevant link in this section as well.

![Example of challenge metadata.](/images/posts/bugfix/fcc_challenge1_metadata.png)

### Identifying the Bug ###

The section that we're most concerned with, however, is the solution section.

![Example of incorrect solution section.](/images/posts/bugfix/fcc_challenge1_solution.png)

A lot of these challenges have `//solution required` in place of an actual solution! 

These solutions can often be as short as one line of code:

![Example of a short solution.](/images/posts/bugfix/fcc_example1_solution.png)

And in other cases, they can be several lines long:

![Example of a long solution.](/images/posts/bugfix/fcc_example2_solution.png)

The important part is that they remain correct.

## Squashing the Bug ##

The process for fixing these remains simple:

1. Solve the exercise.
2. Replace the `//solution required` comment with the full solution.
3. Test the curriculum using the `npm run test:curriculum` command.

All tests should either return as `passing` or `pending`. The results of the `test:curriculum` script returns the following:

![Result of tests on local repository with no changes.](/images/posts/bugfix/fcc_test1_default.png)

7773 passing tests against 810 pending. We are complete once those 16 solutions move from `pending` to `passing`! The curriculum tests takes about 4 minutes to resolve, meaning, it's more effective to test the changes in bulk, as opposed to testing after each individual modification.

I knew I was on the right track after fixing the first test to increment those passing tests by 1 to 7774.

![Result of tests on local repository with one correct change.](/images/posts/bugfix/fcc_test2_success.png)

Now only 15 more to go.

If you were curious to know what a failed test result would look like, you'd get a third notice stating that a test has failed and the script would crash out with an `npm ERR! Test failed.` message. Luckily, as it is incredibly helpful, it tells you exactly which test failed!

![Result of tests on local repository with an incorrect change.](/images/posts/bugfix/fcc_test3_fail.png)

The good thing is that my own tests will fail and crash out after around 7~10 seconds of terminal silence if I've made a mistake since the accessibility exercises are toward the start of the curriculum's challenges. In this one instance, inactivity in the terminal for more than 4 minutes likely means my work was successful!

You're more than welcome to see the exact edits made to the files on the pull request. All challenge fixes were included in one pull request.

![Screenshot of edits made to all the files requiring solutions.](/images/posts/bugfix/fcc_challenges_fixes.png)

## Creating the Pull Request ##

After completing all of my necessary edits, I just needed to make an appropriate pull request.

First, created a new branch that followed contributor naming guidelines for this sort of situation and then checked it out:

```bash
git checkout -b fix/add-accessibility-solutions
```

Now, I could add my files to the commit.

![Screenshot of modified files since last commit.](/images/posts/bugfix/fcc_commit_files.png)

Wait a second, what are all these `*.json` files? It turns out, the project doesn't have a gitignore for stopping the `package.json` and `package-lock.json` files that are created whenever we call `lerna bootstrap` or `lerna exec npm install`. Lerna will actually execute the `npm install` command for every subdirectory that has node-modules within it. This strategy allows freeCodeCamp to exist on one large monorepository. The alternative would be splitting each major subdirectory into their own individual repositories and treating them as their own.

For the most part, I'm seeing these files because I decided to build the project locally. I can *safely* ignore these files and refrain from adding them to my commit because they are generated as part of the build process. Instead, I want to specifically add the files that I know that I edited. While I could add each individually by name, I can also use a wildcard operator to add all of the markdown files to my commit. Only the challenges are markdown files and the markdown files are the ones I want to commit!

```bash
# While in the freeCodeCamp/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/ directory:
git add *.md
```

![Screenshot of modified files added to the current commit.](/images/posts/bugfix/fcc_commit_files2.png)

Now, I can create a commit that is specifically for these edited files. Luckily, the project comes with an `npm run commit` command to help out.

![Missing commit script.](/images/posts/bugfix/fcc_missing_script1.png)

Turns out that the documentation isn't quite up to date!

![Missing commit script reference.](/images/posts/bugfix/fcc_missing_script2.png)

I'll have to make a separate pull request to fix that issue separately. In the meantime, we'll commit our files in the staging area by hand and then discard all the changes made in the working directory by other files.

```bash
# Commit the files added to the staging area.
git commit -m "fix(curriculum): update accessibility challenges related to issue #35751"

# Discard all the other changes made in the working directory by other files.
git checkout -- .
```
After confirming that all of the files pass the appropriate tests...

![Screenshot of all successful tests.](/images/posts/bugfix/fcc_test4_complete.png)

...I can create the pull request.

![Screenshot of creating a pull request.](/images/posts/bugfix/fcc_pull1.png)

After submission, the pull request will automatically trigger a new Travis CI build using the established continuous integration pipeline.

![Screenshot of submitted pull request and pending Travis CI build results.](/images/posts/bugfix/fcc_pull2.png)

Given enough time, the build validated my pull request's changes: it was successful!

![Screenshot of a successful Travis CI build.](/images/posts/bugfix/fcc_pull3.png)

## Other Changes ##

Following all this, I notified the maintainers in the original issue ([#35751](https://github.com/freeCodeCamp/freeCodeCamp/issues/35751)) that my pull request ([#35809](https://github.com/freeCodeCamp/freeCodeCamp/pull/35809)) was been submitted. While reading through the thread, I noticed there were some other issues with the accessibility challenges that needed to be reviewed: specifically for [/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/avoid-colorblindness-issues-by-using-sufficient-contrast.english.md@master](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum/challenges/english/01-responsive-web-design/applied-accessibility/avoid-colorblindness-issues-by-using-sufficient-contrast.english.md).

As pointed out by [@huyenltnguyen](https://github.com/huyenltnguyen) in [this comment](https://github.com/freeCodeCamp/freeCodeCamp/issues/35751#issuecomment-481079680), JS solutions are not full solutions!

So I made a quick edit, solved another challenge, staged and commit my changes, and created another pull request ([#35810](https://github.com/freeCodeCamp/freeCodeCamp/pull/35810)) to close out my contributions to this issue.

![Image of pull request pending build process approval.](/images/posts/bugfix/fcc_pull4.png)

With that, this bug is officially squashed. (Pending their acceptance of my pull requests, of course).

![Image of pull request passing Travis CI build process.](/images/posts/bugfix/fcc_pull7.png)

***

**Updated April 10th, 2019**

As of today, my pull requests have both been merged successfully into the main branch!

Pull Request ([#35809](https://github.com/freeCodeCamp/freeCodeCamp/pull/35809)):

![Screenshot of successful merge.](/images/posts/bugfix/fcc_pull8.png)

Pull Request ([#35810](https://github.com/freeCodeCamp/freeCodeCamp/pull/35810)):

![Screenshot of successful merge.](/images/posts/bugfix/fcc_pull9.png)
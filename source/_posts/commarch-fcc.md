---
title: 'FLOSS in Review: freeCodeCamp'
tags:
  - bugfix
  - education
  - open-source
categories:
  - - blog
    - hfoss
  - freeCodeCamp
photos:
  - /images/posts/bugfix/fcc_banner.png
date: 2019-04-04 23:36:28
---

# FLOSS in Review - freeCodeCamp #

Before I contribute to any organization, I like to do my research to ensure my time is well invested in something that isn't going to shut down in the next few years. I have a feeling freeCodeCamp will be around for quite a while and I'm excited to see it grow. {% post_link bugfix-fcc-35751 You can read my bugfix post here. %}

<!-- Read more -->

## About the Organization ##

![Banner for Free Code Camp.](/images/posts/bugfix/fcc_homepage.png)

freeCodeCamp is an educational, nonprofit organization founded in October 2014 by teacher, software engineer, and freelance developer [Quincy Larson](https://www.linkedin.com/in/quincylarson/) ([@ossia](https://twitter.com/ossia)). After [learning how to code](https://medium.freecodecamp.com/a-cautionary-tale-of-learning-to-code-my-own-eddb24d9d5a7) in a world without a resource like freeCodeCamp, he ended up creating a globally utilized education platform.

### Community ###

If *learners* are users to [One Laptop per Child](http://one.laptop.org/) (OLPC) and the [SugarLabs](https://sugarlabs.org/) teams, freeCodeCamp has its *campers*. freeCodeCamp is a community of millions of people who learn to code with an emphasis placed on collaboration and communication. Alongside their online learning platform are in-person study groups in more than 2,000 cities around the world.

The organization publishes an aggregate column of news from plenty of programmers who write for their publication on [Medium](https://medium.freecodecamp.org/) - at the time of writing this, they are Medium's largest technical publication. In addition, they host a community [forum](https://forum.freecodecamp.org/) for campers to discuss, learn, and grow together.

Here are some other resources that they provide:

- A [YouTube channel](https://youtube.com/freecodecamp) with free courses on Python, SQL, Android, and a wide variety of other languages.
- A [podcast](https://podcast.freecodecamp.org/) with technology insights and inspiring stories from developers.
- [Local study groups](https://study-group-directory.freecodecamp.org/) around the world, where you can code together in person.
- A comprehensive [guide to thousands of programming topics](https://guide.freecodecamp.org/)
- A [Facebook group](https://www.facebook.com/groups/freeCodeCampEarth/permalink/428140994253892/) with over 100,000 members worldwide

### Curriculum ###

The online site offers several areas of study, offering certification for several specific fields of computer science study should a camper complete a course's final five projects. (Most of their courses are estimated to take about 300 hours for the average camper).

Campers can receive certification for these [courses](https://learn.freecodecamp.org/):

- Responsive Web Design
- JavaScript Algorithms & Data Structures
- Front-end Libraries
- Data Visualization
- APIs & Microservices
- Information Security & Quality Assurance

Each of these core certifications are further broken up into a series of subtopics that are easier for campers to manage. Completion of all six of these certifications will net a camper a, "Full Stack Development Certification." You can get that after you've completed around 1,800 hours of coding - and that's if you didn't make any mistakes and get stuck debugging.

### License(s) ###

freeCodeCamp is a donor-supported 501(c)(3) nonprofit organization that maintains an accessible, free full-stack web development curriculum while also maintaining the robust software that keeps their learning platform operational. There are separate licenses for the curriculum itself and for the computer software. On both accounts, however, the Free Software Foundation would approve of freeCodeCamp as being both free as in *pizza* and free as in *liberty*. (*viva la libre*).

**Disclaimer: I am not a lawyer.**

#### The Software - Modified BSD License ####

The computer software is licensed under the [BSD 3-Clause "New", "Modified", or "Revised" License](https://opensource.org/licenses/BSD-3-Clause) license. The [source](https://github.com/freeCodeCamp/freeCodeCamp) is accessible from their GitHub repository.

A permissive agreement similar to the 2-clause BSD license, it states that source and binary code is redistributable, with or without modification, so long as the copyright notice is retained and the name of the copyright holders are not used to endorse or promote products derived from the software itself.

The [Free Software Foundation](https://www.fsf.org/)'s (FSF) Licensing and Compliance Lab states that the Modified BSD license is [compatible with the GNU GPL](https://www.gnu.org/licenses/license-list.en.html). (FSF makes mention that the Modified BSD license can be easily confused for the [*original* BSD license](https://www.gnu.org/licenses/license-list.en.html#OriginalBSD); the fundamentally equivalent [X11 license](https://directory.fsf.org/wiki/License:X11) or [Apache 2.0](https://directory.fsf.org/wiki/License:Apache-2.0) are preferable).

#### The Curriculum - Attribution-ShareAlike 4.0 International License ####

The learning resources are also kept with the source in their own [`/curriculum`](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/curriculum) and [`/guide`](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/guide) subdirectories. The materials found within these folders are under the [Creative Commons Attribution-ShareAlike 4.0 International license](https://creativecommons.org/licenses/by-sa/4.0/) (CC BY-SA 4.0). Users are free to share and adapt any of the curriculum and guide material under the terms of the agreement.

The Free Software Foundation lists both the Creative Commons Attribution 4.0 (CC BY 4.0) and the CC BY-SA 4.0 as free licenses, however, neither should be used on software. While the CC BY 4.0 is fully compatible with all versions of the GNU GPL, CC BY-SA 4.0 is one-way compatible with the GNU GPL version 3. This means while you may license modified versions of CC BY-SA 4.0 material as GNU GPL version 3, you cannot relicense GPL 3 licensed works under CC BY-SA 4.0.

***

## Project Health ##

### Structure ###

![Screenshot of git clone operation information.](/images/posts/bugfix/fcc_git_clone.png)

Overall, the project is doing very well. The repository size is currently settling at a nice 110.5 MB. It doesn't take too long to clone if you have a good internet connection, but, given the focus on providing a quality educational experience for a global population, some might be looking at a longer wait. Luckily, this size is only a barrier for those who want to contribute code. Campers around the world with access to an internet connection will find that the platform itself is pared down to the minimal content per page.

There are [three branches](https://github.com/freeCodeCamp/freeCodeCamp/branches) for the project's [monorepository](https://github.com/freeCodeCamp/freeCodeCamp): [`master`](https://github.com/freeCodeCamp/freeCodeCamp), [`production-current`](https://github.com/freeCodeCamp/freeCodeCamp/tree/production-current), and [`production-legacy-2018`](https://github.com/freeCodeCamp/freeCodeCamp/tree/production-legacy-2018). Aside from this main project, there are over 100 repositories underneath the umbrella organization ([take a look at them here](https://github.com/freeCodeCamp)).

There are over 250 active and over 13,000 closed [issues](https://github.com/freeCodeCamp/freeCodeCamp/issues?q=is%3Aissue+is%3Aopen+sort%3Aupdated-desc) alongside over 2,500 open and over 19,300 [pull requests](https://github.com/freeCodeCamp/freeCodeCamp/pulls?q=is%3Apr+is%3Aopen+sort%3Aupdated-desc), all at the time of writing. The most recent pull request was made [7 minutes ago](https://github.com/freeCodeCamp/freeCodeCamp/pull/35759)! With over 22,567 commits made to master, it's a decently large project for only having been started in [2013, from a `.gitignore`, `LICENSE`, and a `README` markdown file.](https://github.com/freeCodeCamp/freeCodeCamp/tree/7a80dfe1684664cefd2923bdbb329dcb9a48dc4f).

![Screenshot of contribution programming language distribution statistics.](/images/posts/bugfix/fcc_language_distribution.png)

The project is a web application backed by JavaScript, HTML, and CSS. The small percentage of Shell scripts written are used to set up a Docker container for a server hosting the learning platform. According to Stack Overflow's [Developer Survey Results (2018)](https://insights.stackoverflow.com/survey/2018#technology), 69.8% of the 100,000 developers surveyed reported [JavaScript as the most popular programming, scripting, and/or markup language](https://insights.stackoverflow.com/survey/2018#most-popular-technologies). ([Rust, Kotlin, Python, TypeScript, Go, and Swift were all more loved, however](https://insights.stackoverflow.com/survey/2018#most-loved-dreaded-and-wanted)). These signs suggest that the languages supporting freeCodeCamp's infrastructure are going to be around for years to come.

A quick look at the project's [dependency graph](https://github.com/freeCodeCamp/freeCodeCamp/network/dependencies) reveals over 800 dependencies - but this number doesn't account for redundancies. The tool scans the project's package.json files in order to find dependencies and links them to github repositories when possible. It's a Node.js project at heart, so, expect it to have the same kind of [vulnerabilities](https://docs.npmjs.com/auditing-package-dependencies-for-security-vulnerabilities).

Overall the platform is built upon a Node.js based API server, a set of React based client applications, and a set of scripts that are used to evaluate the front-end projects.

### Leadership ###

If anyone were to be the [benelevolent dictator for life](https://en.wikipedia.org/wiki/Benevolent_dictator_for_life), it'd be Quincy. As both the founder and original core contributor, he has the most commits across the total life of the project and is still active (although, not nearly as active as he was when he started out). Anyone who completes at least 10 commits would be within the top 100 contributors. 70 or more gets you to the top twenty. 187 or more will get you to the top ten. And roughly 500 commits will get you top five.

It's not necessarily about the lines of code you write either. The third contributor on the list, ([@Bouncey](https://github.com/Bouncey)) has removed 1,159,292 lines of code and contributed 1,404,038 lines in return - much more than Quincy has. He's not the only mulit-million line contributor on the project *who is still active*. While they have certainly done *a lot* of work, freeCodeCamp welcomes contributors.

Alongside that, like any good educational institution, freeCodeCamp takes measures to help fight against cyberbullying and toxicity over the internet. Their [Code of Conduct](https://www.freecodecamp.org/code-of-conduct) is, "strictly enforced," according to their contribution guide.

But how exactly does the curriculum see change? Is there one person in charge of everything, meticulously planning? No! The curriculum is always being improved in response to user feedback - the community is just as important as the engineers behind it. Many go on to contribute back to the code that helped support their earliest learning attempts. [Instead of preparing for an April Fool's joke](https://twitter.com/ossia/status/1112737225496629249), Quincy and the others worked towards building out a [roadmap for version 7.0 of the curriculum](https://www.freecodecamp.org/forum/t/help-us-build-version-7-0-of-the-freecodecamp-curriculum/263546).

If you're interested in contributing to the new project, you can see [this list of frequently asked questions](https://www.freecodecamp.org/forum/t/freecodecamp-curriculum-7-0-faqs/269346) for more information on how to get started.

### Contribute ###

If you're interested in contributing to this project, it can be daunting to see all of the work put in by the over 3,446 contributors on the main repository alone. There are tons of ways that you can contribute!

As with any open source project, get started by [joining the community](https://www.freecodecamp.org/signin) and [using their platform](https://learn.freecodecamp.org/). Contribution doesn't have to mean programming and extending the open source codebase - it can mean answering questions for other campers, providing feedback, captioning YouTube channel videos, editing articles, fixing typos, and more.

If you find any bugs, be sure to follow their instructions on [their forum post about the subject](https://www.freecodecamp.org/forum/t/how-to-report-a-bug/19543).

If you find any security issues - *don't post it on social media or the GitHub issue tracker*. Email [security@freecodecamp.org](mailto:security@freecodecamp.org) and get them to look at it through there, away from prying eyes that can exploit those vulnerabilities.

If you're looking for something more focused on the codebase, there are plenty of [labels](https://github.com/freeCodeCamp/freeCodeCamp/labels) available to tag issues and pull requests as well. In particular, [`firsttimerswelcome`](https://github.com/freeCodeCamp/freeCodeCamp/labels/first%20timers%20welcome) and [`helpwanted`](https://github.com/freeCodeCamp/freeCodeCamp/labels/help%20wanted) are open to everyone and permission is not required to work on them.

Start by reading through their [contribution guidelines](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/CONTRIBUTING.md).

![Picture of other contributors welcoming me to the fold!](/images/posts/bugfix/fcc_acknowledgements.png)

*Respond to an issue and take a crack at it!*

{% post_link bugfix-fcc-35751 Trust me if I could do it, you can too. %}

***
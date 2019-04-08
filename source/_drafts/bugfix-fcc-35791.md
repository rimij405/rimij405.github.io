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
---

# Squashing Bugs - freeCodeCamp Issue #35791 #

I was in the middle of responding to issue [#35751](https://github.com/freeCodeCamp/freeCodeCamp/issues/35751) for [freeCodeCamp](https://www.freecodecamp.org/), when I found a typo in the local development setup guides! I was writing up the other bugfix report as I churned along, but, wow - I managed to contribute and have my changes accepted for a completely different effort!

To note, this post is for issue `#35791` and **not** the very similarly numbered `#35751`, which I am in the middle of writing another bugfix report for. You'll see my other report on this site once I finish editing files and performing a spell-check. That draft is sitting on my harddrive, so, even if you end up seeing this first, this is my *second* magic trick.

But it's one that resulted in a successful pull request as well!

![Logo for Free Code Camp.](/images/posts/bugfix/fcc_logo.svg)

The nonprofit's mission is simple: help *campers* learn to code. For free. (*And this time, it's free as in pizza **and** free as in libre*). I did a brief review on the Free Code Camp code base in preparation for the {% post_link bugfix-fcc-35751 other bugfix report here %}. {% post_link commarch-fcc You can read my FLOSS review post here. %}

<!-- Read more -->

## Overview ##

I was reading over the [local developer setup guide](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally.md) when I came across an innocuous typo. The link to the contributor's forum hadn't been updated!

![Screenshot of the suspect.](/images/posts/bugfix/fcc_bugfix-link.png)

## The Issue ##

Since I already had read the [contributor's guide](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/CONTRIBUTING.md). I was ready to roll. I went ahead and created issue [#35791](https://github.com/freeCodeCamp/freeCodeCamp/issues/35791). 





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

## Setting Up the Local Environment ##

This isn't my first rodeo with GitHub projects and I consider myself no stranger to command line git, so I wasn't expecting there to be any difficulty at this stage. While contributors can easily do work without setting up a local environment, it's highly recommended for those who are interested in contributing regularly.

When I opened up the guide to setting freeCodeCamp up locally, I was greeted with this:

<!-- markdownlint-disable MD034 -->
{% blockquote Todd Chaffee (@tchaffee) & Mrugesh Mohapatra (@raisedadead), freeCodeCamp https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally.md Set up freeCodeCamp locally %}
<!-- markdownlint-enable MD034 -->
As of 8 March 2019, please consider helping us test our new guide on how to [setup freeCodeCamp locally using Docker](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally-using-docker.md) instead of using this guide. It should result in fewer, if not zero, errors but we won't know until enough devs try it.
{% endblockquote %}

I've never used Docker before, but, I guess it's as good a time as ever.

### Forking the Repository ###

![Screenshot of the forked repository under my account.](/images/posts/bugfix/fcc_fork.png)

This part was easy; you can find my fork [here](https://github.com/rimij405/freeCodeCamp).

### Preparing the Development Environment ###

![Screenshot of the Cmder application.](/images/posts/bugfix/fcc_cmder.png)

I use command line git through git bash; on top of that, I'm using [Cmder](https://cmder.net/) - a neat little console emulator available on Windows - to keep my terminals together. An SSH key has already been set up for my own development environment as well.

![Screen capture of me typing the following paragraph into Visual Studio.](/images/posts/bugfix/fcc_vscode.gif)

I write my code in the same IDE I write my blog posts: [Visual Studio Code](https://code.visualstudio.com). Microsoft might not be known for it's open source technology (yet), but, VS Code is licensed under the [MIT Expat](https://github.com/Microsoft/vscode/blob/master/LICENSE.txt) agreement and can be found on their [GitHub](https://github.com/Microsoft/vscode) repository.

### Cloning a copy of freeCodeCamp ###

![Screenshot of git clone operation information.](/images/posts/bugfix/fcc_git_clone.png)

I forgot to clone from my fork the first time I did this and ended up running:

```bash
git clone git@github.com:freeCodeCamp/freeCodeCamp.git fcc
```

To fix it, I changed into the directory and switched around the remotes:

```bash
cd fcc
git remote add upstream git@github.com:freeCodeCamp/freeCodeCamp.git
git remote remove origin
git remote add origin git@github.com:rimij405/freeCodeCamp.git
```

You can check your remotes with the following command:

```bash
git remote -v
```

![Screenshot of git remotes.](/images/posts/bugfix/fcc_git_remote.png)

Seems like all is good. The next step in the guide was to set up an upstream anyway, so, this ended up getting that done for me.

### Running the local copy ###

This can be useful for previewing edits to the pages as they would appear on the learning platform.

#### Installing prerequisites ####

From the `Docker` guide, we are required to install the stable version of the [community edition](https://docs.docker.com/install/), and the latest LTS version of [`Node.js`](http://nodejs.org/). (We also need `npm`, but that comes bundled with Node).

##### Node.js & npm #####

![Screenshot of Node.js installation helper.](/images/posts/bugfix/fcc_node_install.png)

I installed Node.js first because I knew it would be easy. I've got Node.js experience - no shenanigans there.

##### Docker Desktop for Windows #####

Docker didn't end up working out for me. My copy of Windows (Windows 10 Home) doesn't include Hyper-V; if it did, this would have been much, much easier. Because of this, I'll have to follow the old-school installation instructions.

I've never used Docker and don't pretend to know how it does what it does. I imagine Docker containers are a lot like lightweight virtual machines, but without all the baggage an operating system would carry in the latter situation.

###### Hyper-V vs. VirtualBox ######

Since I'm a no-good, very bad Windows user, I need to install the [Docker Desktop for Windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows). But, this requires some additional tinkering. I need to have [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v) enabled on my system, but, VirtualBox  will no longer work as long as it's enabled.

The problem: I use [VirtualBox](https://www.virtualbox.org/) for development of [Sugar](https://wiki.sugarlabs.org/go/Welcome_to_the_Sugar_Labs_wiki) activities on a [Fedora Spin of Sugar-on-a-Stick](https://wiki.sugarlabs.org/go/Sugar_on_a_Stick). If I can't run VirtualBox, I'm going to have a bad time.

###### The Workaround ######

I sought an a workaround in the meantime and was thankful to find that I wasn't the only one interested in running Hyper-V and VirtualBox on the same system. [Derek Gusoff](https://derekgusoff.wordpress.com/2012/09/05/run-hyper-v-and-virtualbox-on-the-same-machine/) found that one could use the `bcdedit` command in windows in order to edit the `hypervisorlaunchtype` property. 

If you set it to `off` and reboot, you'll be able to use VirtualBox:

```bash
bcdedit /set hypervisorlaunchtype off
```

If you set it to `auto` and reboot, you'll be able to use Hyper-V once again:

```bash
bcdedit /set hypervisorlaunchtype auto
```

As of VirtualBox version 6.0.0, there is some limited support for VM's to run on systems where Hyper-V is activated, but, you're [mileage may vary](https://forums.virtualbox.org/viewtopic.php?f=6&t=90853).

All of these options, although nice, suggest turning to Microsoft for their official solution: when you want to use VirtualBox, turn Hyper-V off and reboot.

You can do it through the control panel:

![Screenshot of deactivating Hyper-V.](/images/posts/bugfix/fcc_hyper-v.png)

Or through a neat little command, if executed with elevated user permissions:

```powershell
Disable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-Hypervisor
```

###### Only Professionals Allowed ######

The good thing is that Docker will install Hyper-V for us. The bad thing? We need to log in just to download the installer.

![Screenshot of downloading Docker installer.](/images/posts/bugfix/fcc_docker-install.png)

So after the registration, password generation, captcha, refreshing, clicking on confirmation codes, email verification, and signing in multiple times I'll be right back...I really hope that I have Microsoft 10 Professional edition.

I was finally able to download Docker CE and was greeted with this:

![Screenshot of a failed Docker installer.](/images/posts/bugfix/fcc_docker-noinstall.png)

At this point, I could have turned back and tried with freeCodeCamp's other installation strategy, but, I figured it didn't hurt to try Docker's [legacy installer](https://docs.docker.com/toolbox/overview/).

##### Docker Toolbox #####

![Screenshot of documentation that says: "Legacy desktop solution. Docker Toolbox is for older Mac and Windows systems that do not meet the requirements of Docker Desktop for Mac and Docker Desktop for Windows. We recommend updating to the newer applications, if possible."](/images/posts/bugfix/fcc_docker-toolbox-notes.png)

"I don't know if this will work, but it doesn't hurt to try." - Me, trying out Docker Toolbox. Basically, Toolbox uses VirtualBox instead of Microsoft's native Hyper-V. There's nothing guaranteeing it will run the server in the way we want it to, but, it's worth a shot.

![Screenshot of shortcuts for Docker Toolbox, after installation.](/images/posts/bugfix/fcc_docker-toolbox-install.png)

I followed the [installation](https://docs.docker.com/toolbox/toolbox_install_windows/) instructions for Docker Toolbox (unchecking the already installed VirtualBox and Git from Windows programs when prompted by the installer).

![Screenshot of Docker Toolbox terminal after verifying installation.](/images/posts/bugfix/fcc_docker-toolbox-success.png)

Then I tested out the `docker run hello-world` command...

![Screenshot of Docker Toolbox terminal after running docker run hello world.](/images/posts/bugfix/fcc_docker-toolbox-success-2.png)

...and the `docker run -it ubuntu bash` command.

![Screenshot of Docker Toolbox terminal after running docker run -it ubuntu bash.](/images/posts/bugfix/fcc_docker_ubuntu.png)

For the Docker Toolbox installation, we would also need to change the `DOCKER_HOST_LOCATION` property in the `.env` file to the output from the `docker-machine ip` command. Unfortunately, getting up to this point doesn't guarantee success. A command that is run later on, as a part of the dependency installation, doesn't play nicely with Toolbox. I had to uninstall my installation and this time, I tried using the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10). I used this guide from [Rio Martinez](https://medium.com/@riomartinez): "[Docker Running Seamlessly in Windows Subsystem [for] Linux](https://medium.com/devopslinks/docker-running-seamlessly-in-windows-subsystem-linux-6ef8412377aa)".

The largest problem is that Docker doesn't yet support the Windows for Subsystem Linux - I made a judgement call to stop trying to figure it out at this point. My next solution would have been to install Docker on my VirtualBox instance of OpenSUSE, but, this had its own headaches associated with it; namely, I'd have to start the process from the beginning, clone the repo to OpenSUSE, and fiddle with VirtualBox's network adapter just to be able to get it to bridge over to my host machine's network. All possible, but, time-consuming. I imagine that I represent an edge case - surely, most others with Hyper-V on their Windows systems would do well to follow the most up-to-date Docker installation notes.

#### Installing dependencies ####

At this point, we could go ahead and change the API keys in freeCodeCamp's setup, but, we are just running it locally to fix some challenge files. We're not focused on getting access to all the different types of services just yet.


Following this, we have to bootstrap the docker images once in order to prep them for running. We can do this by running freeCodeCamp's npm scripts from the project directory.

```bash
npm install --dev --ignore-scripts
npm audit fix
npm run docker:init
npm run docker:install
npm run docker:seed
```

Getting here means the worst is finally out of the way.
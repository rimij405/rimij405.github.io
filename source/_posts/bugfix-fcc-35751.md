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
# - /images/posts/bugfix/fcc_banner.png
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

## Setting Up the Local Environment ##

This isn't my first rodeo with GitHub projects and I consider myself no stranger to command line git, so I wasn't expecting there to be any difficulty at this stage. While contributors can easily do work without setting up a local environment, it's highly recommended for those who are interested in contributing regularly.

When I opened up the guide to setting freeCodeCamp up locally, I was greeted with this:

<!-- markdownlint-disable MD034 -->
{% blockquote Todd Chaffee (@tchaffee) & Mrugesh Mohapatra (@raisedadead), freeCodeCamp https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally.md Set up freeCodeCamp locally %}
<!-- markdownlint-enable MD034 -->
As of 8 March 2019, please consider helping us test our new guide on how to [setup freeCodeCamp locally using Docker](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally-using-docker.md) instead of using this guide. It should result in fewer, if not zero, errors but we won't know until enough devs try it.
{% endblockquote %}

This is my way of clarifying that *I did not use Docker* to setup the local environment - {% post_link triage-docker-on-wsl my attempts resulted in a fruitless four-hour triage attempt that could have been solved by using a virtual machine %} to begin with.

Instead, I went with the legacy approach: build freeCodeCamp locally using MongoDB, Node.js, and npm. This method I knew would work - I've had prior experience using my computer for this type of development.

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

### Building the local copy ###

This can be useful for previewing edits to the pages as they would appear on the learning platform.

#### Installing dependencies ####

From the `Docker` guide, we are required to install the stable version of the [community edition](https://docs.docker.com/install/), and the latest LTS version of [`Node.js`](http://nodejs.org/). (We also need `npm`, but that comes bundled with Node). Docker didn't end up working out for me. My copy of Windows (Windows 10 Home) doesn't include Hyper-V; if it did, this would have been much, much easier. Because of this, I had to follow the old-school installation instructions: MongoDB would have to do.

##### Node.js & npm #####

![Screenshot of Node.js installation helper.](/images/posts/bugfix/fcc_node_install.png)

I installed Node.js first because I knew it would be easy. I've got Node.js experience - no shenanigans there.

##### MongoDB Community Edition #####

Since I'm working from Windows, I followed MongoDB Community Edition's installation [guidelines](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/#install-mdb-edition). I installed MongoDB as a service, but, you may need to install it in a different way for your system. Mongo's database instance starts as a part of the service installation process, but, since I often work in Git Bash for Windows, I wanted to make sure the `mongo` and `mongod` commands were accessible from the `PATH` environment variable.

I opened up my `.bashrc` file and added something along the lines of this to my script:

```bash
# Inside ~/.bashrc, ~/.bash_profile, or ~/.profile
if [ -d "/<...>/MongoDB/Server/<version>/bin" ] ; then
  export PATH="/<...>/MongoDB/Server/<version>/bin:$PATH"
fi
```

What the above script does is check to see if the MongoDB directory exists and the adds it to the `PATH` variable. Be sure to replace `<...>` and `<version>` appropriately when setting this up for yourself.

After editing the configuration file, either logout and log back into bash or source the file you've edited appropriately:

```bash
source ~/.bashrc
```

With that, you can `echo "$PATH"` to confirm it's been added correctly. Be sure to wrap the `PATH` variable in quotes when evaluating to ensure whitespace doesn't mess with your terminal.

If you want to see the first element in your PATH variable, you can use the following script - and don't forget to check your version of Mongo to ensure the installation was correct!

![Animation of the following bash script being executed in the terminal Git Bash for Windows.](/images/posts/bugfix/fcc_path_example.gif)

<!--- Source: https://unix.stackexchange.com/questions/65932/how-to-get-the-first-word-of-a-string -->

```bash
# Get first element in the PATH.
echo "$PATH" | head -n1 | sed -e 's/:.*$//'

# Check mongo and mongodb versions, respectively.
mongo --version
mongodb --version
```

#### Configure Dependencies ####

Next up: setting up the environment variables specific to Free Code Camp's build process.

```bash
# Create a copy of the "sample.env" and name it ".env".
# Populate it with the necessary API keys and secrets:
copy sample.env .env
```

Since the keys in the `.env` file are not required to be changed in order to run the app locally, I left the default values from sample.env as-is.

*(NB: Before editing any of the code, I made sure to checkout a local branch called `master-local`. I always like to be on the safe side!)*

Following that a call to `npm ci` will install the project's dependencies. In my scenario, I also had to install [`lerna`](https://github.com/lerna/lerna#readme) globally. Lerna is a package manager's package manager so-to-speak. It's really for projects with a large amount of packages to maintain.

##### Troubleshooting Installation #####

**Be warned!** If you don't install lerna prior to executing `npm ci` it will just hang at the `lerna bootstrap` command that is called during the installation process. For me, I had to execute `lerna exec npm install` instead just to get the project's dependencies to install in the first place.

In addition, on Windows, there was an issue running the commands from the base system - instead, I needed to start an elevated PowerShell instance with administrator privileges:

<!--- Reference: https://serverfault.com/questions/464018/run-elevated-powershell-prompt-from-command-line -->

```bash
# Start a new powershell instance in-line, in the current working directory, using Git Bash.
powershell $pwd
```

```powershell
# Start an elevated instance in a new window.
Start-Process PowerShell -Verb RunAs
```

From there, I was able to complete the development process!

### Running Local ###

With a quick call to `npm install` to ensure everything was properly installed, followed by an `npm run bootstrap`, the dependencies were ready. My instance of MongoDB was primed and ready - so with `npm seed`, the database was filled with test data provided by the repository.

Underneath everything, the curriculum is just a Node.js application. I felt like I recognized what it was that I was looking at when I built a development environment with `npm develop`. With a welcoming, `DONE Compiled successfully in 52127ms` - we did it.

I could now see my copy on the localhost.

***

## Solving the Challenges ##
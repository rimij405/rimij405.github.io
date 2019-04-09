---
title: 'Triage - Troubleshooting Docker on WSL'
date: 2019-04-05 20:38:45
tags:
  - bugfix
  - education
  - open-source
  - docker
  - triage
  - bugfix
categories:
  - - blog
    - hfoss
  - freeCodeCamp
photos:
  - /images/posts/triage/docker_triage.png
---

# I Can't Dock Here. #

During my journey to the center of the (core) bugfix, I came across some disheartening issues regarding Docker and Windows 10 Home. For the most part, Windows 10 Professional, Windows 10 Enterprise, and Windows 10 Education are all unaffected by this problem. {% post_link bugfix-fcc-35751 I discovered this while trying to build freeCodeCamp locally for a bugfix. %}

As full disclosure, this post does **not contain a solution** for the issue that caused the Docker installation process to fail. This post has been made to highlight my process and share the steps I have taken, to help others who come across it.

<!-- Read more -->

## Overview ##

The most recent and recommended version of Docker is [Docker Desktop for Windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows). For native Windows (and for this operating system alone) it requires Hyper-V virtualization. I am running on a copy of Windows 10 Home - the one distribution that Microsoft provides that doesn't include this feature.

While I could get a copy of Windows 10 *Education* from my [university](https://www.rit.edu), this wouldn't be time- or cost-effective. If I could solve the problem on my own desktop, it would be a benefit to myself and others. Besides, freeCodeCamp's contributors wanted feedback on their [guide to using Docker in order to build the codebase](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally-using-docker.md).

When I opened up the guide to setting freeCodeCamp up locally, I was greeted with this:

<!-- markdownlint-disable MD034 -->
{% blockquote Todd Chaffee (@tchaffee) & Mrugesh Mohapatra (@raisedadead), freeCodeCamp https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally.md Set up freeCodeCamp locally %}
<!-- markdownlint-enable MD034 -->
As of 8 March 2019, please consider helping us test our new guide on how to [setup freeCodeCamp locally using Docker](https://github.com/freeCodeCamp/freeCodeCamp/blob/master/docs/how-to-setup-freecodecamp-locally-using-docker.md) instead of using this guide. It should result in fewer, if not zero, errors but we won't know until enough devs try it.
{% endblockquote %}

I had never used Docker before, so this seemed as good a time as any.

## The Workaround Attempts ##

From the `Docker` guide, we are required to install the stable version of the [community edition](https://docs.docker.com/install/), and the latest LTS version of [`Node.js`](http://nodejs.org/). (We also need `npm`, but that comes bundled with Node). I was able to install Node.js (bringing npm alongside it) with no issue. Since I'm a no-good, very bad Windows user, I needed to install the [Docker Desktop for Windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows), but, when it came to Docker, I quickly found out about the Hyper-V dependency - one that I couldn't address given my operating system.

In order to install the correct version of Docker, I would need to install and enable [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v) on my system. However, VirtualBox will not work as long as Hyper-V virtualization is enabled. It seemed that [I would no longer be able to use my distributions through VirtualBox or VMWare](https://superuser.com/questions/1208850/why-virtualbox-or-vmware-can-not-run-with-hyper-v-enabled-windows-10). This, however, was out of date: as of VirtualBox 6.0.0, the releases for VirtualBox (see: [VirtualBox 6.0 changelog](https://www.virtualbox.org/wiki/Changelog)) would include support for the Windows Hypervisor Platform accelerator (WHPX) - the same one that QEMU (see: [QEMU 2.12 changelog](https://wiki.qemu.org/ChangeLog/2.12)) uses. This is, however, experimental. There is some limited support for VirtualBox's ability to run on systems parallel to Hyper-V, but, you're [mileage may vary](https://forums.virtualbox.org/viewtopic.php?f=6&t=90853)

I wasn't the only one interested in running Hyper-V and VirtualBox on the same system. [Derek Gusoff](https://derekgusoff.wordpress.com/2012/09/05/run-hyper-v-and-virtualbox-on-the-same-machine/) found that one could use the `bcdedit` command in windows in order to edit the `hypervisorlaunchtype` property to toggle Hyper-V.

If you set it to `off` and reboot, you'll be able to use VirtualBox:

```bash
bcdedit /set hypervisorlaunchtype off
```

If you set it to `auto` and reboot, you'll be able to use Hyper-V once again:

```bash
bcdedit /set hypervisorlaunchtype auto
```

This is remarkably close to Microsoft's official solution as well: when you want to use VirtualBox, turn Hyper-V off and reboot.

You can do it through the control panel:

![Screenshot of deactivating Hyper-V.](/images/posts/bugfix/fcc_hyper-v.png)

Or through a neat little command, if executed with elevated user permissions:

```powershell
Disable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-Hypervisor
```

I could toggle back and forth, but, rebooting takes time and I'd like to avoid having a schedule where I must restart my machine just in order to get work done - I don't dual-boot operating systems for a reason; it's inconvienient.

The problem: I use [VirtualBox](https://www.virtualbox.org/) for development of [Sugar](https://wiki.sugarlabs.org/go/Welcome_to_the_Sugar_Labs_wiki) activities on a [Fedora Spin of Sugar-on-a-Stick](https://wiki.sugarlabs.org/go/Sugar_on_a_Stick). If I can't run VirtualBox, I'm going to have a bad time.

It was time to find a workaround.

### The Brute Force Approach ###

I figured there was no harm in trying to install the latest software even though I had none of the proper dependencies installed. The good thing is that Docker claimed that Hyper-V would be installed alongside Docker, if we ran the installation manager. The bad thing? I don't like the fact that you have to log in to get the installer - this takes valuable time!

![Screenshot of downloading Docker installer.](/images/posts/bugfix/fcc_docker-install.png)

After the registration, password generation, captcha, refreshing, clicking on confirmation codes, email verification, and signing in multiple times just to get back to the download page, it felt bad to see this all fall apart. The problem with this approach started as soon as I got to the download page. Installing Docker Desktop for Windows would automatically install Hyper-V - but only if I had a qualifying version of Windows 10 that could support it. This means that *Home* users have no modern support for using Docker on their systems.

The fact that VirtualBox couldn't run parallel to Hyper-V suddenly *didn't* matter. The problem, specific to my version of the Windows 10 operating system, means that Hyper-V couldn't be installed on my machine, even if I wanted to be able to use it. The Docker installer's first check is to see if your machine has Hyper-V enabled.

![Screenshot of a failed Docker installer.](/images/posts/bugfix/fcc_docker-noinstall.png)

*Bummer*. Even if I didn't have the need to use VirtualBox, I still wouldn't have been able to get around Docker Desktop's need for Hyper-V.

### Docker Toolbox ###

I didn't give up hope just yet. At this point, I could have turned back and tried with freeCodeCamp's other installation strategy (as I would later do), but, I figured it didn't hurt to try Docker's [legacy installer](https://docs.docker.com/toolbox/overview/).
![Screenshot of documentation that says: "Legacy desktop solution. Docker Toolbox is for older Mac and Windows systems that do not meet the requirements of Docker Desktop for Mac and Docker Desktop for Windows. We recommend updating to the newer applications, if possible."](/images/posts/bugfix/fcc_docker-toolbox-notes.png)

"I don't know if this will work, but it doesn't hurt to try." - Me, trying out Docker Toolbox. Basically, Toolbox uses VirtualBox instead of Microsoft's native Hyper-V. There's nothing guaranteeing it will run the server in the way we want it to, but, it's worth a shot.

![Screenshot of shortcuts for Docker Toolbox, after installation.](/images/posts/bugfix/fcc_docker-toolbox-install.png)

I followed the [installation](https://docs.docker.com/toolbox/toolbox_install_windows/) instructions for Docker Toolbox (unchecking the already installed VirtualBox and Git from Windows programs when prompted by the installer).

![Screenshot of Docker Toolbox terminal after verifying installation.](/images/posts/bugfix/fcc_docker-toolbox-success.png)

Then I tested out the `docker run hello-world` command...

![Screenshot of Docker Toolbox terminal after running docker run hello world.](/images/posts/bugfix/fcc_docker-toolbox-success-2.png)

...and the `docker run -it ubuntu bash` command.

![Screenshot of Docker Toolbox terminal after running docker run -it ubuntu bash.](/images/posts/bugfix/fcc_docker_ubuntu.png)

For the Docker Toolbox installation, we would also need to change the `DOCKER_HOST_LOCATION` property in the `.env` file to the output from the `docker-machine ip` command. Unfortunately, getting up to this point doesn't guarantee success.

When I tried running docker from PowerShell, it was clear that I wasn't getting the support I needed. Attempting to build the project with the installed docker tools sent back error after error. It was easy enough to get hello-world running, but, I don't want to have to modify the installation script used in freeCodeCamp's project.json just to get off the ground.

*Sigh*. On to the next one.

### Windows Subsystem for Linux ###

I decided to take a shot at installing [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10) on my system. (Finally, a feature that all Windows 10 users can try). It seemed pretty straightforward. I tried installing Docker by following this [guide](https://medium.com/devopslinks/docker-running-seamlessly-in-windows-subsystem-linux-6ef8412377aa) from [Rio Martinez](https://medium.com/@riomartinez).

I uninstalled Docker Toolbox using Docker's complete uninstallation steps and gave my system a fresh reboot. From there, I installed the optional WSL feature through PowerShell in order to acitvate the subsystem:

```PowerShell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

After searching for a Linux Distro that was compatible with Docker, I settled on Canonical Group Ltd.'s [Ubuntu version 18.04 LTS](https://www.microsoft.com/store/p/ubuntu/9nblggh4msv6). Ubuntu on Windows seemed promising. I launched the new bash terminal after installing, created my user account, and updated my distro's packages with:

```bash
sudo apt update && sudo apt upgrade
```

All seemed to be going well, but, by the time I get to the end of it I had errors appearing due to the way Windows mounted WSL to the system. Officially, Docker states that they don't support the Windows Subsystem for Linux. Ugh - so close yet so far away.

### Host via VirtualBox ###

The largest problem is that Docker doesn't yet support the Windows for Subsystem Linux - I made a judgement call to stop trying to figure it out at this point, but, I have my hunches as to what would work should you find yourself in this situation.

I recommend you look at what (FLOSS) operation systems (besides Windows) officially support Docker and create a guest in VirtualBox based on that distro. If the distro has the official support, if you can get it to run on your system, then you should finally be able to get Docker up and running. There may be some caveats, however.

Technically, my instance of OpenSUSE should have been able to run Docker, but, much of my troubleshooting moved away from being about Docker and more towards fixing my setup for VirtualBox's network adapter. It's a time-consuming process and one that I believe represents an edge case. Surely, most others with Hyper-V on their systems would never have to go down this route, assuming Docker works as it says it does.

For now, I suggest using Ubuntu 16.04 LTS - the latest 'approved' distro that Docker claims to support in an official capacity. For now, I'll be building my code the old fashioned way - setting up a backend with an instance of MongoDB giving persistence to a Node.js server.
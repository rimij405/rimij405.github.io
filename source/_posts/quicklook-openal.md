---
title: 'Quicklook: FLOSS Alternatives to OpenAL'
tags:
  - open-source
  - class
  - audio
  - game development
  - quicklook
categories:
  - - blog
    - hfoss
date: 2019-04-03 12:19:21
---

# OpenAL #

[OpenAL](https://www.openal.org/) is a cross-platform 3D audio API for software applications that require audio. There's just one thing: it's open as in *open-API* not *open-source*. OpenAL, like OpenGL, attempts to avoid being vendor-specific. That's great for interoperability, but, not so great for the tenets of free software.

***

## OpenAL Soft ##

[OpenAL Soft](http://openal-soft.org/) is a fork of the OpenAL project, way back from when it was open-source on an SVN repository. OpenAL Soft's [source] is hosted on GitHub and is provided under the [GNU Lesser General Public License](https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License) (LGPL).

### Functionality ###

For the most part, it's like OpenAL, except for some important differences in terms of support for certain extensions (like it's lack of support for Vorbis and MP3).

### Contributions? ###

You can get in touch with the developers of OpenAL Soft with the same [mailing list](https://openal-soft.org/) that you would use for OpenAL. Although the OpenAL project itself *is* free-of-cost, it isn't open-source. Despite this, the community hasn't split over a hostile fork - they embrace one another. There are about 35 contributors in total, but, no explicit contribution guides exist. Suggestions are to get in touch with the developers through the mailing list.

***

## Port Audio ##

[PortAudio](http://www.portaudio.com/), on the other hand, is a cross-platform, open-source audio I/O library. Originally released under a custom, permissive license, the most recent version was released under the [MIT License](http://opensource.org/licenses/mit-license.php).

### Functionality ###

The library itself, "provides a very simple API for recording and/or playing sound using a simple callback function or blocking read/write interface." Notably, it's not suggested to use this library for file I/O - it has no support for reading or writing formatted audio files like .wav and .aiff. Instead, 

### Contributions? ###

The project uses [Assembla](http://www.assembla.com/) for hosting its [source](https://www.assembla.com/spaces/portaudio/git/source) via a git repository. If you're interested in [contributing](http://www.portaudio.com/volunteer.html) to Port Audio, they are seeking experienced 'C' audio developers, writers and documentation experts, and engineers with unit testing and continuous integration experience.

PortAudio maintains a [partial list of contributors](http://www.portaudio.com/people.html) on its website. A [mailing list](http://www.portaudio.com/contacts.html) and its archive is also facilitated through the website. Bug reports can be submitted through their [ticket tracker](https://app.assembla.com/spaces/portaudio/tickets/realtime_list). 

***

## RtAudio ##

[RtAudio] is a set of C++ classes that provide a common, cross-platform API for realtime audio input/output. The RtAudio license is similar (but not the same) as the MIT License. It is, however, undeniably open-source.

### Functionality ###

The library was designed with the following objectives:

- object-oriented C++ design.
- simple, common API across all supported platforms.
- only one source and one header file for easy inclusion in programming projects.
- allow simultaneous multi-api support.
- support dynamic connection of devices.
- provide extensive audio device parameter control.
- allow audio device capability probing.
- automatic internal conversion for data format, channel number representation, (de)interleaving, and byte-swapping.

### Contributions? ###

You can view the [source](https://github.com/thestk/rtaudio) on RtAudio's GitHub repository. There are about [19 open issues](https://github.com/thestk/rtaudio/issues?q=is%3Aissue+is%3Aopen+sort%3Aupdated-desc) on the project's issue tracker, with the [most recent one](https://github.com/thestk/rtaudio/issues/196) being written one day prior (at the time of writing this blog post).

## libsndfile ##

[libsndfile](http://www.mega-nerd.com/libsndfile/). It's released under the terms of the GNU Lesser General Public License (LGPL) - you can use libsndfile with any software as long as it's used as a dynamically loaded library and it abides by a small number of other conditions. 

### Functionality ###

libsndfile is a C library for reading and writing files containing sampled audio data. It is designed to allow the reading and writing of many different sampled sound file formats (such as MS Windows WAV and the Apple/SGI AIFF format) through one standard library interface. During read and write operations, formats are seamlessly converted between the format the application program has requested or supplied and the file's data format.

This doesn't playback audio, but, it does the crucial work involved in file I/O and format conversion.

### Contributions? ###

libsndfile was created by [Erik de Castro Lopo](mailto:erikd@mega-nerd.com). You can submit bugs by submitting a ticket through the project's [issue tracker](https://github.com/erikd/libsndfile/issues). You can find the source [here](https://github.com/erikd/libsndfile). You can read more about contributing [here](https://github.com/erikd/libsndfile/blob/master/CONTRIBUTING.md).
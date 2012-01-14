---
layout: post
title: "mediasite_extract_content"
date: 2012-01-13 19:54
comments: true
categories: 
---
Mediasite is a set of webcasting solutions offered by Sonic Foundry. One of the products in the mediasite family is a lecture capturing platform. The end product provided by Mediasite is an embeddable webplayer that plays the video of lecturer in one window and simultaneously flipping through the slides. Slide transition times occur just as during the original lecture.

I wrote a Python script that parses the content of a Mediasite lecture and creates DV-formatted videos of the lecture and the slideshow. In my case these videos are useful for the sake of combining them into a single video which will then be uploaded to Vimeo. The command line tools `ffmpeg` and `mencoder` are required.

Below is more information about installing `ffmpeg` and `mencoder`, and the script is as follows.

<!-- more -->

{% gist 1609649 mediasite_slides_movie.py %}

# Installing `ffmpeg` and `mencoder`
## Mac OS X
### `mencoder` with Homebrew
A user who has `homebrew` installed presumably has read/write access to the right system directories, and the commands are simply

    brew install ffmpeg
    brew install mplayer

### `mencoder` with downloaded binaries
Not having read/write access to the right system directories on a certain system, I found a different approach, which is to download the binaries and update the script to use the correct location.

The MEncoder binary can be downloaded from the bottom of this [post](http://stefpause.com/apple/mac/mplayer-os-x-10rc1-and-mencoder-binaries/).

### ffmpeg with Homebrew
A user who has `homebrew` installed presumably has read/write access to the right system directories, and the commands are simply

    brew install ffmpeg
    brew install mplayer

### `ffmpeg` from source
This [post](http://jungels.net/articles/ffmpeg-howto.html) provides instructions on building ffmpeg from source. It's likely that one needs the extra libraries installed with XCode to build this from source.

### `ffmpeg` binary

The ffmpegX project (which seems to be defunct) provides a command-line binary in the OS X package. Download it, install it, and then edit the script to use the `ffmpegX` binary located at `Applications/ffmpegX.app/Contents/MacOS/ffmpegX`.


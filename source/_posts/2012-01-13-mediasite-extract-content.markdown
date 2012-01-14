---
layout: post
title: "mediasite_extract_content"
date: 2012-01-13 19:54
comments: true
categories: 
---
Mediasite is a set of webcasting solutions offered by Sonic Foundry. One of the products in the mediasite family is a lecture capturing platform. The end product provided by Mediasite is an embeddable webplayer that plays the video of lecturer in one window and simultaneously flipping through the slides. Slide transition times occur just as during the original lecture.

I wrote a Python script that parses the content of a Mediasite lecture and creates DV-formatted videos of the lecture and the slideshow. In my case these videos are useful for the sake of combining them into a single video which will then be uploaded to Vimeo.

and here it is.

<!-- more -->

{% gist 1609649 mediasite_slides_movie.py %}


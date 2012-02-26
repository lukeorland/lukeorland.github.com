---
layout: post
title: "Doxygen 1.8.0, Markdown, and the OS X app"
date: 2012-02-26 10:48
comments: true
categories: 
---

Doxygen's brand new support of Markdown has attracted my attention. I tried out the Doxygen.app for OS X. Here are a couple of notes-to-self about this Doxywizard GUI.

* Doxygen 1.8.0 newly supports the Markdown format. However, Doxygen.app does not know to look for `*.markdown` or `*.md` source files. Those filename matching patterns must be added to the list in *Expert* -> *Input* -> *FILE_PATTERNS*.
* It does not automatically load up the `Doxyfile` located in the specified base project directory. Use the Doxywizard menu to open or save the configuration.

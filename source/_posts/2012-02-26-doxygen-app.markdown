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

Also, I was getting an error message when configuring the dot output to pdf:

    Format: "pdf" not recognized. Use one of: canon cmap cmapx cmapx_np dot eps fig gd gd2 gif gv imap imap_np ismap jpe jpeg jpg plain plain-ext png ps ps2 svg svgz tk vml vmlz vrml wbmp xdot
    Problems running dot: exit code=1, command='/usr/local/bin/dot'`

The solution is to reinstall graphviz, building it with Cairo/Pango support.

From this [comment](https://github.com/voormedia/rails-erd/issues/12#issuecomment-1145048):

> - Uninstall Cairo, Pango and Graphviz (`brew uninstall cairo pango graphviz`)
> - Install Cairo, Pango and Graphviz, exactly in this order (`brew install cairo pango graphviz`)


---
layout: post
title:  "Debugging Return Values in Visual Studio"
date:   2014-01-11 23:00:00
categories: jekyll update
---

Debugging functions that use other function's return values as their arguments just go a whole lot easier with Visual Studio 2013.

Check out this incredibly useful summary of the four most relevant return values after stepping over the code the breakpoint is on:

![Return Values Screenshot]({{ site-url }}/assets/return-values-screenshot.png)

* No more stepping into the function just to see what its arguments were
* No more wishing you **had** stepped into the function
* No more //drilling down// by hand in the locals window
* No more copying and pasting into the watch window
* No more getting exceptions thrown for re-calling methods with side-effects from the immediate window

This, my friends, is progress!  This changes everything.

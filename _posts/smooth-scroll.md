---
layout: post
title:  "Add Smooth Scrolling to Visual Studio"
date:   2014-02-01 01:19:45
categories: visualstudio
---

Over the last few days I have been lamenting the lousy scrolling in Visual Studio.  I have an Alps touchpad on my laptop that supports two-finger intertial scrolling and it works perfectly in Chrome.  The scrolling is so smooth you can actually read it while it is scrolling and it is really easy to maintain your context on a web page that doesn't fit on a screen.

Unfortunately when I switch to Visual Studio, although the two-finger geture works, it is extraordinarily chunky, not at all like the buttery smooth scrolling I have come to be so fond of.  So I tested some apps: Chrome, Internet Explorer, Microsoft Word all scroll the document with sufficient precision so it looks like the the content is actually moving.  Furthermore, the touchpad supports inertia and an easily executed fast two-finger swipe continues scrolling and gradually comes to a halt.


Being a programmer, the first question that came to mind was how is this two-finger inertial scrolling implemented?  What API is being used?  What Windows messages are being sent?  So I fired up Spy++ and directed it track messages sent to the Chrome window and the important messages look like this:
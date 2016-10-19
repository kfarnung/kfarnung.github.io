---
layout: post
title: Ubuntu 8.04 on the Thinkpad T60
date: 2008-10-04 23:44:13 -0500
categories: [linux]
---
Well, as typically happens with me, I got bored and decided to try something new.  This time it was Ubuntu Linux on my trusty Thinkpad T60.  I hadn't tried Linux in quite some time and was pleasantly surprised by my experience.

First, my specs:
<ul>
  <li>Core 2 Duo T7200 2.0GHz</li>
  <li>2GB DDR2</li>
  <li>120GB HD</li>
  <li>ATI Radeon X1400 128MB</li>
  <li>DVD Burner</li>
  <li>Intel Pro/Wireless 3945</li>
</ul>

To start, I was excited that my wireless worked right out of the box with my family's WPA protected network.  The install worked flawlessly and I was soon booted into a working operating system.  After connecting to the wireless network, I rescanned the repositories and installed all of the provided updates.  That's all it takes to get completely up to date.

One of the other things I was really interested in trying out was Compiz Fusion, also knows as "Desktop Effects" in Ubuntu.  Trying to enable them using the default "radeon" driver did not work, but enabling the proprietary fglrx driver allowed them to work flawlessly.  Although ATI has had a spotty past with their Linux support, this seems to be a very good step forward for them.  Even suspending and resuming the computer works almost perfectly.

As far as other hardware, I have yet to try the bluetooth, but it is detected by the operating system when enabled, which is encouraging.  In time I will hopefully try that out, but it's not really high on the list of priorities.  I've also neglected the modem since I really don't have a use for it, but it looks to require the Linuxant proprietary drivers (which cost money).

The touchpad worked perfectly right out of the box and Ubuntu does provide a small number of options to configure it.  One of the problems I did have was the sensitivity of the scroll, but that was easily fixed using a small Xorg configuration change.  Just add the following line to the touchpad section of the xorg.conf file:

<blockquote><code>Option		"VertScrollDelta"	"130"</code></blockquote>

A higher number (up to 255 I'm assuming) seems to make the scroll go slower, while a lower number seem to make it scroll faster.  As far as the TrackPoint, it worked perfectly as a mouse, but the center scroll button did not function.  This was also easily fixed with a few more tweaks to the xorg.conf file.  Just add the following to the "Configured Mouse" section of the xorg.conf file:

<blockquote><code>Option		"EmulateWheel"	"true"
Option		"EmulateWheelButton"	"2"</code></blockquote>

Since I seem to have most of the hardware under control (my biggest concern), I'm spending most of my time trying out new applications and learning about everything that a modern operating system has to offer.
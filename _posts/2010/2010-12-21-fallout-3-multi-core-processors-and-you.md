---
layout: post
title: Fallout 3, Multi-Core Processors, and You
date: 2010-12-21 17:31:06 -0800
categories: [windows]
---
Fallout 3: Game of the Year Edition was only $20 on Steam last night, so I finally decided to pick up a copy.  I've played a lot of the game already on the Xbox 360, so I'm pretty familiar with the beginning areas, but I spent most of that time dealing with an annoying bug where the game would freeze, but not crash.  I could no longer control the game, but the ambient audio continues to play; the only resolution being to kill the process.  Needless to say, it really ruins the experience in the game and worst yet, it seems to be a really common problem for anyone who has more than two processor cores (I have eight, so the problem is multiplied further).  There doesn't appear to be any sort of official fix, but people have reported success with some [custom modifications](http://www.pdsys.org/blog/post/2009/02/07/Fallout-3-VideoDisplay-Freezes-sound-keeps-going.aspx) to the configuration.

The game engine has some issues with processors that have more than 2 cores. You can force the game to only use two of them and it will stop the freezing. I haven't had it freeze once since I did this several days ago.

Open up the **fallout.ini** file in **My Documents\My Games\Fallout3**

Find the line:

    bUseThreadedAI=0

change it to:

    bUseThreadedAI=1

Add another line after it and insert:

    iNumHWThreads=2

This will limit the game to 2 cores and prevent the engine bug from causing the game to freeze.
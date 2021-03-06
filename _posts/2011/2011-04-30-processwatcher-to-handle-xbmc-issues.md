---
layout: post
title: ProcessWatcher to handle XBMC issues and crashes
date: 2011-04-30 00:55:00 -0700
categories: [windows]
---
I've been using XBMC for enjoying video and music on my TV, but have constantly encountered a bug where the video gets choppy if I've left XBMC open for too long.  To help remedy the situation without needing a full PC restart or the aid of a keyboard, I've created a simple tool that will monitor the XBMC process (or any process for that matter) and restart it if it exits.

I call the tool [ProcessWatcher]({{ "/content/processwatcher-to-handle-xbmc-issues/ProcessWatcher.zip" | relative_url }}) and have decided to release it as a free download.

It does require that you have [.NET Framework 4.0](http://www.microsoft.com/downloads/en/details.aspx?FamilyID=9cfb2d51-5ff4-4491-b0e5-b386f32c0992&amp;displaylang=en) installed.

Usage Instructions:

1.  Unzip the downloaded file to a convenient location (like **C:\Tools\ProcessWatcher\**).
2.  Create a new shortcut in Windows.  Point the shortcut to the ProcessWatcher.exe file and name the shortcut whatever you'd like (I call mine "XBMC").
3.  Right-click on the newly created shortcut and choose "Properties."
4.  To the end of the "Target" field you will need to add the full path to the XBMC.exe file.  On 32-bit systems this will likely be **"C:\Program Files\XBMC\XBMC.exe"** (Don't forget to include the quotes) and on 64-bit systems this will likely be **"C:\Program Files (x86)\XBMC\XBMC.exe"** (Again, don't forget to include the quotes).
5.  Change the "Start in" field to match the path you found the XBMC.exe file in (For example **C:\Program Files (x86)\XBMC\**).
6.  Change the icon using the "Change Icon..." button to whatever you'd like (I used the XBMC icon).
7.  Click "OK" in the properties dialog and double-click the shortcut to launch XBMC via ProcessWatcher.

If at any point the XBMC.exe process exits (either intentionally or via a crash), the ProcessWatcher will count down and then restart the process.  While ProcessWatcher is counting down, you can hit the enter key (if the window has focus) or click "Quit" to abort the countdown immediately and exit the application.  If the countdown elapses, then XBMC will be started up again.
---
layout: post
title: ProcessWatcher to handle XBMC issues and crashes
date: 2011-04-30 00:55:48 -0800
categories: [windows]
---
I've been using XBMC for enjoying video and music on my TV, but have constantly encountered a bug where the video gets choppy if I've left XBMC open for too long.  To help remedy the situation without needing a full PC restart or the aid of a keyboard, I've created a simple tool that will monitor the XBMC process (or any process for that matter) and restart it if it exits.

I call the tool ProcessWatcher and have decided to release it as a free download:
<a href="http://storage.kylefarnung.com/ProcessWatcher.zip">http://storage.kylefarnung.com/ProcessWatcher.zip</a>

It does require that you have .NET Framework 4.0 installed:
<a href="http://www.microsoft.com/downloads/en/details.aspx?FamilyID=9cfb2d51-5ff4-4491-b0e5-b386f32c0992&amp;displaylang=en">http://www.microsoft.com/downloads/en/details.aspx?FamilyID=9cfb2d51-5ff4-4491-b0e5-b386f32c0992&amp;displaylang=en</a>

Usage Instructions:
<ol>
  <li>Unzip the downloaded file to a convenient location (like <strong>C:\Tools\ProcessWatcher\</strong>).</li>
  <li>Create a new shortcut in Windows.  Point the shortcut to the ProcessWatcher.exe file and name the shortcut whatever you'd like (I call mine "XBMC").</li>
  <li>Right-click on the newly created shortcut and choose "Properties."</li>
  <li>To the end of the "Target" field you will need to add the full path to the XBMC.exe file.  On 32-bit systems this will likely be <strong>"C:\Program Files\XBMC\XBMC.exe"</strong> (Don't forget to include the quotes) and on 64-bit systems this will likely be <strong>"C:\Program Files (x86)\XBMC\XBMC.exe"</strong> (Again, don't forget to include the quotes).</li>
  <li>Change the "Start in" field to match the path you found the XBMC.exe file in (For example <strong>C:\Program Files (x86)\XBMC\</strong>).</li>
  <li>Change the icon using the "Change Icon..." button to whatever you'd like (I used the XBMC icon).</li>
  <li>Click "OK" in the properties dialog and double-click the shortcut to launch XBMC via ProcessWatcher.</li></ol>

If at any point the XBMC.exe process exits (either intentionally or via a crash), the ProcessWatcher will count down and then restart the process.  While ProcessWatcher is counting down, you can hit the enter key (if the window has focus) or click "Quit" to abort the countdown immediately and exit the application.  If the countdown elapses, then XBMC will be started up again.
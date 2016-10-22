---
layout: post
title: Windows 7 and TortoiseSVN problems
date: 2010-12-21 17:15:34 -0800
categories: [windows]
---
For quite a while now I've been having issues with TortoiseSVN reporting that files were corrupt while updating and submitting.  After my working copy became corrupt, yet again, I decided to do some research and turned up a [solution to the problem](http://serverfault.com/questions/72561/64-bit-tortoisesvn-on-windows-7-says-file-or-directory-is-corrupted-and-unreadab).  Apparently there is a bug, introduced in Windows 7, with the MoveFileEx command that TortoiseSVN uses quite frequently.  The fix is now included in Windows 7 SP1.

[Download Windows 7 SP1](https://www.microsoft.com/en-us/download/details.aspx?id=5842)
---
layout: post
title: Harmony Remotes and Xbox 360 Power on Delays
date: 2011-04-30 12:09:11 -0800
categories: [technology]
---
It appears that there can be a handshake issue between some receivers (like my Denon AVR-2311CI) and the Xbox 360 console (like my "Fat" 60GB Pro model).  The issue occurs if the Xbox 360 is powered on too quickly after the receiver is powered on.  This seems like a simple fix, but from what I've been reading online there isn't a clear solution to the problem of delaying the Xbox 360 power on.

Here is my solution.[teaserbreak]
<ol>
  <li>Launch the Harmony Remote Software (I'm using version 7.7.0).</li>
  <li>Find the activity (or activities) which utilize your Xbox 360 and click "Settings."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony1.png"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony1.png" /></a></div></li>
  <li>Choose "Review the settings for this Activity" and click "NEXT >."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony2.PNG"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony2.PNG" /></a></div></li>
  <li>Choose "Yes, but I want to add more control of options and devices for this Activity." and click "NEXT &gt;."</li>
  <li>You should not need to add any additional devices, so just click "SAVE."</li>
  <li>Click next through all of the input questions until you reach the "Please review the actions for your &lt;Activity Name&gt; Activity" (My activity is called "Play Xbox 360").<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony3.png"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony3_small.png" /></a></div></li>
  <li>The key to adding the delay is to power on the Xbox 360 yourself within the activity startup actions.  Select your Xbox 360 from the "Add action for" dropdown box and then click "Add &gt;."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony4.png"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony4_small.png" /></a></div></li>
  <li>Choose "Send this infrared delay" and select "5 seconds," then click "NEXT &gt;" (I used 5 seconds in my setup, but yours might be able to be shorter or need to be even longer).<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony5.PNG"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony5.PNG" /></a></div></li>
  <li>Select the Xbox 360 again from the "Add action for" dropdown box and then click "Add >."</li>
  <li>Choose "Send this infrared Command" and select "PowerOn" before clicking "NEXT &gt;."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony6.PNG"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony6.PNG" /></a></div></li>
  <li>At this point there should be two additional "Xbox 360" options added to the activity startup.  If so, then click "SAVE &gt;."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony7.PNG"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony7_small.png" /></a></div></li>
  <li>Choose "Yes, these settings are correct." and click "NEXT &gt;."</li>
  <li>To complete this part of the configuration, click "DONE" twice.</li>
  <li>Since we are now powering on the Xbox 360 ourselves, we need to remove the power on command from the Xbox 360 device.</li>
  <li>Go to the "Devices" tab of the interface, locate the Xbox 360 device, and click "Settings."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony8.PNG"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony8.PNG" /></a></div></li>
  <li>Choose "Adjust power settings" and click "NEXT &gt;."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony9.PNG"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony9.PNG" /></a></div></li>
  <li>Choose "I want to turn off this device when it's not in use" and click "NEXT &gt;."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony10.PNG"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony10_small.png" /></a></div></li>
  <li>Choose "A button on the remote for On, and a different button for Off" and click "NEXT &gt;."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony11.PNG"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony11.PNG" /></a></div></li>
  <li>Choose "I don't have the original remote, but I know what command that is used" and select "-None-" before clicking "NEXT &gt;."<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony12.PNG"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony12_small.png" /></a></div></li>
  <li>The next screen will prompt "No command was selected.  Would you like to continue?"  Click the "YES" button to continue.<br /><div class="image_block"><a href="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony13.PNG?mtime=1304193114"><img alt="" src="http://kylefarnung.com/media/blogs/kylefarnung/harmony/harmony13.PNG?mtime=1304193114" width="398" height="92" /></a></div></li>
  <li>Make sure the "I don't have the original remote, but I know the command that is used" option is chosen with the "PowerOff" command selected and click "NEXT &gt;."</li>
  <li>Leave the options on the next screen and just click "NEXT &gt;" again.</li>
  <li>Finally, click "DONE" three times to return to the main interface.</li>
  <li>At this point you can update your remote normally and test out the modifications.</li>
</ol>

Although I haven't tested this extensively, it seems to resolve my initial issue perfectly.  The one downside I've found is that the "Help" function will no longer work to turn the Xbox 360 on if it failed to do so.  You will either need to choose the device on the remote and send the "PowerOn" command directly or use another remote/controller to turn it on.  At this point I'm willing to live with it, but will update if I end up finding a better way.
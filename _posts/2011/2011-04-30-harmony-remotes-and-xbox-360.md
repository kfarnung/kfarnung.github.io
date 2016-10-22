---
layout: post
title: Harmony Remotes and Xbox 360 Power on Delays
date: 2011-04-30 13:01:00 -0700
categories: [technology]
---
It appears that there can be a handshake issue between some receivers (like my Denon AVR-2311CI) and the Xbox 360 console (like my "Fat" 60GB Pro model).  The issue occurs if the Xbox 360 is powered on too quickly after the receiver is powered on.  This seems like a simple fix, but from what I've been reading online there isn't a clear solution to the problem of delaying the Xbox 360 power on.

Here is my solution:

1.  Launch the Harmony Remote Software (I'm using version 7.7.0).
2.  Find the activity (or activities) which utilize your Xbox 360 and click "Settings."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony1.png)" | relative_url }}

3.  Choose "Review the settings for this Activity" and click "NEXT >."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony2.png)" | relative_url }}

4.  Choose "Yes, but I want to add more control of options and devices for this Activity." and click "NEXT &gt;."
5.  You should not need to add any additional devices, so just click "SAVE."
6.  Click next through all of the input questions until you reach the "Please review the actions for your &lt;Activity Name&gt; Activity" (My activity is called "Play Xbox 360").

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony3.png)" | relative_url }}

7.  The key to adding the delay is to power on the Xbox 360 yourself within the activity startup actions.  Select your Xbox 360 from the "Add action for" dropdown box and then click "Add &gt;."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony4.png)" | relative_url }}

8.  Choose "Send this infrared delay" and select "5 seconds," then click "NEXT &gt;" (I used 5 seconds in my setup, but yours might be able to be shorter or need to be even longer).

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony5.png)" | relative_url }}

9.  Select the Xbox 360 again from the "Add action for" dropdown box and then click "Add >."
10. Choose "Send this infrared Command" and select "PowerOn" before clicking "NEXT &gt;."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony6.png)" | relative_url }}

11. At this point there should be two additional "Xbox 360" options added to the activity startup.  If so, then click "SAVE &gt;."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony7.png)" | relative_url }}

12. Choose "Yes, these settings are correct." and click "NEXT &gt;."
13. To complete this part of the configuration, click "DONE" twice.
14. Since we are now powering on the Xbox 360 ourselves, we need to remove the power on command from the Xbox 360 device.
15. Go to the "Devices" tab of the interface, locate the Xbox 360 device, and click "Settings."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony8.png)" | relative_url }}

16. Choose "Adjust power settings" and click "NEXT &gt;."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony9.png)" | relative_url }}

17. Choose "I want to turn off this device when it's not in use" and click "NEXT &gt;."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony10.png)" | relative_url }}

18. Choose "A button on the remote for On, and a different button for Off" and click "NEXT &gt;."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony11.png)" | relative_url }}

19. Choose "I don't have the original remote, but I know what command that is used" and select "-None-" before clicking "NEXT &gt;."

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony12.png)" | relative_url }}

20. The next screen will prompt "No command was selected.  Would you like to continue?"  Click the "YES" button to continue.

    > ![]({{ "/images/harmony-remotes-and-xbox-360/harmony13.png)" | relative_url }}

21. Make sure the "I don't have the original remote, but I know the command that is used" option is chosen with the "PowerOff" command selected and click "NEXT &gt;."
22. Leave the options on the next screen and just click "NEXT &gt;" again.
23. Finally, click "DONE" three times to return to the main interface.
24. At this point you can update your remote normally and test out the modifications.

Although I haven't tested this extensively, it seems to resolve my initial issue perfectly.  The one downside I've found is that the "Help" function will no longer work to turn the Xbox 360 on if it failed to do so.  You will either need to choose the device on the remote and send the "PowerOn" command directly or use another remote/controller to turn it on.  At this point I'm willing to live with it, but will update if I end up finding a better way.
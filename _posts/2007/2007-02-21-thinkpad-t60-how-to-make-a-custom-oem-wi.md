---
layout: post
title: ThinkPad T60 - How to Make a Custom OEM Windows CD
date: 2007-02-21 19:45:44 -0500
categories: [windows]
redirect_from: /2007/02/21/thinkpad_t60_how_to_make_a_custom_oem_wi/
---
<blockquote><strong>Now updated for Windows XP SP3, if you encounter any problems, please let me know!</strong>

Please note that the RVM Update Pack and KB896256 hotfix are no longer necessary with Service Pack 3.</blockquote>

When I first bought my Lenovo ThinkPad T60, I was a little disappointed at the absence of a normal OEM Windows XP CD. This CD would allow the user to install their own copy of Windows free of the preloaded garbage that comes on every machine. After reading some posts and tutorials and running into problems, I finally have the solution for ThinkPad T60 owners. The CD that is created in this tutorial embeds the Lenovo OEM key (different from the one on the bottom of the machine) and doesn't require activation as long as it's installed on the same machine the license came with.

<del>The problem I had previously where the machine would continually reboot when trying to load Windows seems to have been solved by integrating the KB896256 hotfix into the install. Although I haven't tested this yet myself, a [forum user](http://forum.thinkpads.com/viewtopic.php?p=253393#253393) has reported that installing this hotfix in Safe Mode resolved the issue. Please be cautious when trying this out and make sure you have a backup before doing anything catastrophic, I cannot be held responsible for any damage as a result of this tutorial.</del> <ins>(This is no longer relevant if you integrate SP3!)</ins>

A lot of the initial inspiration came from [this guide](http://www.4saad.com/WhatsNew/Fresh_XP_Install/index.htm), but everything here has been recreated from scratch to customize for T60 owners. This may work on other Lenovo models, but some of the instructions are likely to change slightly (mainly the drivers and hotfix). Anyway, let's get started.

<strong>Update:</strong> I tried out the install last night and it seemed to work well. Windows booted up fine the first time and I had only minor problems with System Update not properly installing things. This may or may not have been caused by the slipstreaming, but if anyone is willing to experiment, you can easily leave out the network drivers and update pack (make sure to still use the Intel Storage Matrix Driver <del>and the KB896256 Hotfix</del>).

<blockquote><strong>If you have any suggestions or problems, please post a comment below!</strong></blockquote>

<strong>Downloads</strong>
<ul>
  <li>Drivers
  <ul>
    <li>[Ethernet (Intel PRO/1000 LAN adapter software) for Windows 2000/XP](http://www-307.ibm.com/pc/support/site.wss/document.do?sitestyle=lenovo&amp;lndocid=MIGR-62922)</li>
    <li>[Intel Matrix Storage Manager Driver for Windows 7 (32-bit), Vista (32-bit) and XP (32-bit)](http://support.lenovo.com/en_US/downloads/detail.page?DocID=DS000795)</li>
    <li>One of the following wireless drivers (Optional)
    <ul>
      <li>[Intel PRO 2200bg, 2915abg, 3945bg, and 3945abg Mini PCI adapter wireless software for Windows 2000, XP](http://www-307.ibm.com/pc/support/site.wss/document.do?sitestyle=lenovo&amp;lndocid=MIGR-62875)</li>
      <li>[Wireless LAN adapter software (ThinkPad 802.11bg, 802.11abg) for Windows 2000 and XP](http://support.lenovo.com/en_US/downloads/detail.page?DocID=DS003567)</li>
      <li>[Wireless LAN ThinkPad 11abgn for Windows 2000, XP](http://www-307.ibm.com/pc/support/site.wss/document.do?sitestyle=lenovo&amp;lndocid=MIGR-66449)</li>
    </ul>
    </li>
  </ul>
  </li>
  <li>Tools
  <ul>
    <li>[nLite 1.4.7 or Newer](http://www.nliteos.com/download.html)</li>
    <li>[Magical Jelly Bean Keyfinder v1.51](http://www.magicaljellybean.com/keyfinder.shtml)</li>
    <li><a href="http://www.kylefarnung.com/media/blogs/kftheblog/wxp.zip" title="">Windows XP CD Package</a></li>
  </ul>
  </li>
  <li>Updates
  <ul>
    <li><del>[Hotfix KB896256](http://support.microsoft.com/kb/896256) (<em>Essential</em>)</del></li>
    <li><del>[Windows XP Service Pack 2 Network Installation Package](http://www.microsoft.com/downloads/details.aspx?FamilyId=049C9DBE-3B8E-4F30-8245-9E368D3CDB5A&amp;displaylang=en) (<em>Essential</em> even if your computer came with SP2)</del> <ins>(Windows XP SP3 has been released!)</ins></li>
    <li><del>[RVM Update Pack 2.1.7 or Newer](http://www.ryanvm.net/msfn/updatepack.html)</del> (Not currently recommended as I have not tested it)</li>
    <li><ins>[Windows XP Service Pack 3 Network Installation Package](http://www.microsoft.com/downloadS/details.aspx?familyid=5B33B5A8-5E76-401F-BE08-1E1555D4F3D4&amp;displaylang=en) (<em>Essential</em>)</ins></li>
  </ul>
  </li>
</ul>

<strong>Preparation</strong>
<ol>
  <li>Download all of the necessary files listed above.</li>
  <li>Install nLite using the provided installer package.</li>
  <li>Run the Magic Jelly Bean Keyfinder to retrieve the currently installed CD Key for use later.  Write this number key down or save it in a text file.</li>
  <li>Execute the driver packages to extract them.  By default the packages should extract to <strong>C:\DRIVERS\WIN</strong>, but please make sure you know where they are being extracted to.</li>
  <li>Extract the Windows XP CD Package (wxp.zip) to a drive with at least a few gigabytes of free space.  The package includes the necessary CD indentification files that aren't copied on to your hard drive. Note that the package does not include <strong>any</strong> actual install files, those come from your computer.</li>
  <li>Open the <strong>cds</strong> folder that you just extracted and then open the <strong>wxphome</strong> or <strong>wxppro</strong> folder depending on the version of Windows that came installed on your computer.</li>
  <li>Do not modify or remove any of the files in this folder since it will become the root of your CD.  Copy (don't move) the <strong>C:\I386</strong> folder containing the Windows install files into this folder so it becomes a subdirectory (ex. <strong>C:\cds\wxppro\I386\</strong>).</li>
  <li>Optionally, the <strong>SUPPORT</strong> and <strong>VALUEADD</strong> folders can similarly be copied into this folder since they are part of the original XP CD.
  <div class="image_block"><img src="http://www.kylefarnung.com/media/blogs/kftheblog/wxp-oem-01.png" alt="View of folder after preparation" title="Windows XP OEM Screenshot 1" width="340" height="193" /><div class="image_legend">This is what the folder should look like after it has been prepared.  In my example I used the wxppro folder since my computer came with Windows XP Pro installed.</div></div>
  </li>
</ol>

<strong>Creating the CD</strong>
<ol>
  <li>Start the nLite program and click <em>Next</em>.</li>
  <li>Click <em>Browse...</em> and browse for your Windows installation folder (either <strong>wxphome</strong> or <strong>wxppro</strong>).
  <div class="image_block"><img src="http://www.kylefarnung.com/media/blogs/kftheblog/wxp-oem-02.png" alt="Locating the Windows installation" title="Windows XP OEM Screenshot 2" width="450" height="356" /><div class="image_legend">This is what the screen should look like if you correctly located your Windows installation folder.</div></div>
  </li>
  <li>Click <em>Next</em> twice to get to the "Task Selection" screen. Select the <em>Service Pack</em>, <em>Hotfixes and Update Packs</em>, <em>Drivers</em>, <em>Unattended</em>, and <em>Bootable ISO</em> tasks and click <em>Next</em>.
  <div class="image_block"><img src="http://www.kylefarnung.com/media/blogs/kftheblog/wxp-oem-03.png" alt="Task Selection" title="Windows XP OEM Screenshot 3" width="450" height="356" /><div class="image_legend">Make sure your Task Selection screen looks like this.</div></div>
  </li>
  <li>On the "Service Pack" screen, click <em>Select</em> to locate the Service Pack <del>2</del> <ins>3</ins> install file.  If a message comes up saying that "Previous Hotfixes have been detected," hit the <em>Yes</em> button to remove them.  Once the <em>Browse</em> window comes up, locate the executable for Service Pack 2, it should be called <strong><del>WindowsXP-KB835935-SP2-ENU.exe</del> <ins>WindowsXP-KB936929-SP3-x86-ENU.exe</ins></strong> and click <em>Open</em>.  Wait for the slipstream to complete and click the <em>OK</em> button when it says "Integrated install has completed successfully."  Make sure the version is now reported as "Windows XP &lt;Version&gt; <del>Sp2</del> <ins>Sp3</ins>" and click <em>Next</em>.</li>
  <li><del>On the "Hotfixes and Update Packs" screen, click the <em>Insert</em> button and locate the "RVMUpdatePack" you downloaded.  Do the same with the KB896256 hotfix.  There should now be two items listed and you should click <em>Next</em> to proceed.</del>
  <div class="image_block"><img src="http://www.kylefarnung.com/media/blogs/kftheblog/wxp-oem-04.png" alt="Hotfixes and Update Packs" title="Windows XP OEM Screenshot 4" width="450" height="356" /><div class="image_legend">This is what the screen should look like after the correct items have been added.</div></div>
  </li>
  <li>On the "Drivers" screen, click the <em>Insert</em> button and click <em>Single driver</em>. To add the Intel Storage Matrix driver, navigate to the driver folder (usually <strong>C:\DRIVERS\WIN\IMSM</strong>) and choose the file <strong>iaahci.inf</strong>. Select "Textmode driver" and only "Intel(R) 82801GBM SATA AHCI Controller (Mobile  ICH7M)" and click <em>OK</em>.
  <div class="image_block"><img src="http://www.kylefarnung.com/media/blogs/kftheblog/wxp-oem-05.png" alt="Storage Device Textmode Drivers" title="Windows XP OEM Screenshot 5" width="450" height="435" /><div class="image_legend">Make sure the selections match before clicking OK.</div></div>
  </li>
  <li>To add the ethernet driver, click the <em>Insert</em> button and click <em>Single driver</em>. Navigate to the Intel PRO/1000 LAN driver folder (usually <strong>C:\DRIVERS\WIN\ETHERNET\PRO1000\WS03XP2K</strong>) and choose the file <strong>e1e5132.inf</strong>.</li>
  <li>Optionally, you can do the same for the wireless driver by going to the correct driver folder (usually <strong>C:\DRIVERS\WIN\WLANINT\XP\Drivers</strong> for Intel PRO/Wireless) and choosing the correct file (<strong>NETw39x5.inf</strong> for Intel PRO/Wireless).</li>
  <li>Once all the drivers are added, click the <em>Next</em> button to continue.
  <div class="image_block"><img src="http://www.kylefarnung.com/media/blogs/kftheblog/wxp-oem-06.png" alt="Drivers" title="Windows XP OEM Screenshot 6" width="450" height="356" /><div class="image_legend">The driver integration screen should look similar to this.</div></div>
  </li>
  <li>On the "Unattended" screen, you can modify a large number of options for the installer, but I only recommend filling in the product key.
  <div class="image_block"><img src="http://www.kylefarnung.com/media/blogs/kftheblog/wxp-oem-07.png" alt="Unattended" title="Windows XP OEM Screenshot 7" width="450" height="356" /><div class="image_legend">I recommend filling in the product key only and leaving the other options alone.</div></div>
  </li>
  <li>When you click the <em>Next</em> button, you will be prompted with "Do you want to start the process?" If everything is correct on the previous screens, you should click <em>Yes</em> to make the modifications.</li>
  <li>Once the "Processing..." screen is finished, click the <em>Next</em> button to continue.</li>
  <li>On the "Bootable ISO" screen, you can choose whether to create an image, burn a CD, or burn an image that you have created previously. I usually create an image to test out on a virtual machine before burning.  You can choose any label you want, but I usually use the label "WXPFPP_EN" since it is the label used on all Windows XP Professional CDs I've dealt with.  Once all of the settings are correct, hit the <em>Make ISO</em> or <em>Burn</em> button.  If you chose to create an image, you will be prompted for a location to save it.
  <div class="image_block"><img src="http://www.kylefarnung.com/media/blogs/kftheblog/wxp-oem-08.png" alt="Bootable ISO" title="Windows XP OEM Screenshot 8" width="450" height="356" /><div class="image_legend">The settings I use to make an ISO for testing in a virtual machine before burning to CD.</div></div>
  </li>
  <li>Once the burn or image is complete, click the <em>Next</em> button and then the <em>Finish</em> button to exit the program.</li>
  <li>If you chose to make an image earlier, you need to burn it to CD before trying to install on your ThinkPad. One free program I recommend is [ImgBurn](http://www.imgburn.com/) (and it even works on Vista).</li>
</ol>

<strong>Using the CD</strong>
<ol>
  <li>Before you do anything else, please make sure to backup your important data! It is also highly recommended that you create your recovery discs if you haven't already and manually back up the Lenovo folders from the C drive. The folders to grab are <strong>drivers</strong>, <strong>I386</strong>, <strong>SUPPORT</strong>, <strong>SWSHARE</strong>, <strong>SWTOOLS</strong>, and <strong>VALUEADD</strong> which should all fit comfortably on a DVD.  Some of the installers under <strong>SWTOOLS</strong> can only be found in this folder and not online.</li>
  <li>Make sure your laptop is set to "AHCI" under "Config"->"SATA" in the BIOS and that you are able to boot from a CD. If it is set to "Compatibility," there may be problems if you try to switch it to "AHCI" after the install.</li>
  <li>If you want to remove the recovery partition (make sure you created your recovery disks <em>before</em> doing anything), you need to disable the "Predesktop Area" under "Security" in the BIOS.</li>
  <li>Boot with the CD in the drive and you may have to "Press any key to boot from CD..." if the drive already has Windows installed.</li>
  <li>On the partition screen you should be able to delete both partitions (system and recovery) and create one or two custom partitions. I personally use 40GB for C and the rest of my 120GB drive for D and that works well for me, but this is an entirely personal thing.</li>
  <li>The rest of the install should go like normal except that you won't have to enter a key during the install.  All other prompts should be there just as they once were.</li>
  <li>After the install, you should immediately have network access over either ethernet or wireless (if you added the drivers) and should immediately run Windows Update.  I wouldn't bother with the drivers at first, but make sure to get both versions of the .NET Framework (v1.1 and v2.0) so that you can install [System Update](http://www-307.ibm.com/pc/support/site.wss/document.do?sitestyle=lenovo&amp;lndocid=MIGR-66956) if desired.</li>
  <li>From here you are basically on your own and more information can be found on [Lenovo's](http://www.lenovo.com/) site and at the [thinkpads.com Support Community](http://forum.thinkpads.com/) where I usually check in a few times per day.</li>
</ol>

<strong>Notes</strong>
<ul>
  <li>If you use System Update, it might continually say that the Intel Storage Matrix Driver isn't installed and even after you tell it to install again, it will still keep coming up.  This didn't happen to me when I tried it and can safely be ignored.</li>
  <li>It will most likely be necessary to install the driver package for your wireless card again after the install has completed. At least with my Intel PRO/Wireless 3945, Access Connections wouldn't work with it until I installed the driver again, even though Windows was able to connect with it just fine. The main reason for integrating the driver is to get wireless immediately so this isn't a problem for me, but you can always leave it out if this bothers you.</li>
  <li>.NET 3.0 refused to install via Windows Update, but installed just fine when I downloaded the installer from Microsoft.  This may be related to the RVM Update Pack, but I'm not sure at this time.</li>
  <li>Some packages don't show up in System Update 3.0 and others don't seem to install properly.  I don't believe this is related to the Windows install, but it's a possibility.  It seems that the best way to install Lenovo software is to use the [Driver Matrix](http://www-307.ibm.com/pc/support/site.wss/document.do?lndocid=TPAD-MATRIX).</li>
</ul>
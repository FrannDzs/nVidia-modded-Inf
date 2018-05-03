### nVidia modded Inf project created 2017 by CHEF-KOCH under GNU GENERAL PUBLIC LICENSE v3.

This project is unofficial and not in any relationship or support with nVidia Cooperation. 

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/fold_left.svg?style=social&label=Follow%20%40CHEF-KOCH)](https://twitter.com/FZeven)
[![Say Thanks!](https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg)](https://saythanks.io/to/CHEF-KOCH)
[![Discord](https://discordapp.com/api/guilds/204394292519632897/widget.png)](https://discord.me/NVinside)

What is a modded INF?
===================

All drivers come with an "Installation INF(ormation) file". This tells the installer how to install the driver. The INF has the instructions to what files to copy and where. It will also setup settings to install with. The INF also has a list of products that it will install for.

nVidia provides UDA (Unified Driver Architecture) where the driver should work for all their released GPUs. So the driver itself will support ALL GPUs, but the INF the driver comes with will only support a selected set of GPU

nVidia by default don't support laptop GPUs with beta and WHQL driver updates on their server. This is left up to the OEM to organize. I assume nVidia must charge to have an OEM driver made or be included, as they are very rear for OEM to actually update a video driver. So an OEM driver has specific instructions for that laptop (ie model specific) and will only work with a select few laptops.

For example a Toshiba OEM driver with a Toshiba INF (nvts.inf) will only work with the models included in that INF.


Modded drivers will NEVER transform your GPU to another one, and will NEVER add features that you do not already have.


Keep in mind:

Fermi GPU's (400 and 500 series) as from 396 driver are official no longer supported!



Remove your old nVidia driver:
===================

1) Extract Display Driver Uninstaller (DDU) and start it, boot into safe mode and clean it. You not need to uninstall the driver or any package via Windows own uninstaller program first. 
2) Reboot Windows and install your modded nVidia driver.



Easy installation:
===================


* Download and extract the Driver (download from official source) - wait until the installer has unzipped the files e.g. to C:\Nvidia
* Search "nv_disp.cat" (or corresponding file) in 'Display.Driver Folder'
* Follow the Video instruction to install the certificate
* Now you can install all my modded drivers, without disabling 'driver signature enforcement' in Windows.



Troubleshoot
===================


before installing


bcdedit -set loadoptions DISABLE_INTEGRITY_CHECKS

bcdedit -set TESTSIGNING ON



after installing

bcdedit -set loadoptions ENABLE_INTEGRITY_CHECKS

bcdedit -set TESTSIGNING OFF



After executing these two commands you need to reboot your OS.



How to sign your driver?
===================

1.) Download and install (or portable) [SelfCert](https://www.pluralsight.com/blog/software-development/selfcert-create-a-self-signed-certificate-interactively-gui-or-programmatically-in-net).

Select: 
x.500 distinguished name: cn=name_here,o=org_here,e=email@example.com

Key size: 2048

Valid from: today

Valid to: Your choice like 5 up to 10 years

2). Now put in a password in and save as PFX

CN = Microsoft Windows Hardware Compatibility PCA
O = Microsoft Corporation
L = Redmond
S = Washington
C = US
E = Your Email

3.) OK now that you have your PFX, you can generate a CAT for your modded driver and sing it (you will need the latest Windows Driver Kit)
4.) Re-generate a new CAT with Inf2Cat like
	Inf2Cat /driver:<path_to_folder_with_INF_&_Files> /os:Vista_X86,Vista_X64,Server2008_X86,Server2008_X64,7_X86,7_X64,Server8_X64,8_X86,8_X64,Server6_3_X64,6_3_X86,6_3_X64
5.) Sign the new CAT with your PFX
	signtool sign /f <filename>.pfx /p <password> "<path_to_folder>\nv_disp.cat"
6). Timesamp your CAT
	signtool timestamp /t http://timestamp.verisign.com/scripts/timstamp.dll "<path_to_folder>\nv_disp.cat"
7.) Now what you need to do, is get the cert from your PFX, install it in the Trusted Root Cert. Auth. and get the reg from this to give to users to apply



ToDo:
======

* Add video (?)
* Add more instruction and project details in Readme.md 
* Mention nvFlash and DDU
* ~~Add manual 'create own inf' section + selfsign~~
* Add 'how to install driver manually' + video?
* ~~Add Devide Id list~~
* ~~Add branch list~~
* I only support win x64 modded infs, do not ask for 7, 8 or x86 versions!
* Fix the markdown ... 


Research and tools:
===================

* https://github.com/Wagnard/display-drivers-uninstaller
* http://forums.guru3d.com/showthread.php?t=377158
* https://laptopvideo2go.com/
* https://forums.geforce.com/default/topic/467215/geforce-driver-installation-guide-a-guide-to-ensure-your-drivers-are-installed-properly-/
* https://forums.geforce.com/default/topic/862424/geforce-drivers/windows-10-faq-and-driver-installation-tips-/

#### nVidia modded Inf project created 2017 by CHEF-KOCH under GNU GENERAL PUBLIC LICENSE v3.

<p align="center">
  <img src="https://github.com/CHEF-KOCH/nVidia-modded-Inf/blob/master/geforce.png" width="350"/>
  <img src="https://github.com/CHEF-KOCH/nVidia-modded-Inf/blob/master/inf%20mod.png?raw=true" width="350"/>
</p>

This project is unofficial and not in any relationship or supported by nVidia Cooperation. 

This project only support x64 Windows 10 versions, if you like to [see x86 ask nVidia to extend the support](https://www.anandtech.com/show/12191/nvidia-to-cease-driver-development-for-32bit-operating-systems) or make a pull request. 

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/fold_left.svg?style=social&label=Follow%20%40CHEF-KOCH)](https://twitter.com/CKsTechNews)
[![Say Thanks!](https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg)](https://saythanks.io/to/CHEF-KOCH)
[![Discord](https://discordapp.com/api/guilds/418256415874875402/widget.png)](https://discord.me/CHEF-KOCH)


What is a modded INF?
===================

All drivers come with an "Installation INF(ormation) file". This tells the installer how to install the driver. The INF has the instructions to what files to copy and where. It will also setup settings to install with. The INF also has a list of products that it will install for.

nVidia provides UDA (Unified Driver Architecture) where the driver should work for all their released GPUs. So the driver itself will support ALL GPUs, but the INF the driver comes with will only support a selected set of GPU

nVidia by default don't support laptop GPUs with beta and WHQL driver updates on their server. This is left up to the OEM to organize. I assume nVidia must charge to have an OEM driver made or be included, as they are very rear for OEM to actually update a video driver. So an OEM driver has specific instructions for that laptop (ie model specific) and will only work with a select few laptops.

For example a Toshiba OEM driver with a Toshiba INF (nvts.inf) will only work with the models included in that INF.

Modded drivers will NEVER transform your GPU to another one and will NEVER add features that you do not already have.


**Reasons for modding**
* You like to test a newer driver which is not available for your card.
* New feature tests.
* It could be used to force installation of newer drivers on OEM locked GPU's.
* You need an older driver that is not officially supported for your GPU because you have a specific application that is broken in newer ones and you cannot wait for a fix.


**Keep in mind**:

> Fermi GPU's (400 and 500 series) as from 396 driver are official no longer supported!



Remove old nVidia drivers
===================

* Extract [Display Driver Uninstaller (DDU)](https://github.com/CHEF-KOCH/nVidia-modded-Inf/tree/master/tools) and start it, boot into safe mode and let DDU auto-clean and restart you. You not need to uninstall the driver or any package via Windows own uninstaller program firstwhen you use DDU but keep in mind that **DDU should only be used in case you get troubles while uninstalling/installing the driver with nVidia's own Setup**, it's not recommend and needed to use DDU as 'normal' driver removal, nVidia's own setup routine usually does the job fine.
* Reboot Windows and install your modded nVidia driver, if the driver isn't signed you need to do it yourself or disable driver signature enforcement under Windows.



Modded Inf Driver installation
===================

* Download and extract the Driver (download from official source) - wait until the installer has unzipped the files e.g. to `C:\Nvidia`.
* Search for e.g. "nv_disp.cat" (or corresponding file) in 'Display.Driver Folder'.
* Follow the Video/written instruction to install the certificate manually (optional).
* Now you can install all my modded drivers, without disabling 'driver signature enforcement' in Windows.



Troubleshoot
===================


Before you install unsigned drivers, you have to manually set these parameters via adminstrative command prompt:

```
bcdedit -set loadoptions DISABLE_INTEGRITY_CHECKS

bcdedit -set TESTSIGNING ON
```


After you're finished installing the unsigned driver:

```
bcdedit -set loadoptions ENABLE_INTEGRITY_CHECKS

bcdedit -set TESTSIGNING OFF
```


After executing these two commands you need to reboot Windows in order to apply the changes.



How to sign your driver?
===================

Download and install (or portable) [SelfCert](https://www.pluralsight.com/blog/software-development/selfcert-create-a-self-signed-certificate-interactively-gui-or-programmatically-in-net).

Select the following after starting the app:
```
x.500 distinguished name: cn=name_here,o=org_here,e=email@example.com

Key size: 2048

Valid from: today

Valid to: Your choice like 5 up to 10 years
```

Now put in a password in and save as PFX

```
CN = Microsoft Windows Hardware Compatibility PCA
O = Microsoft Corporation
L = Redmond
S = Washington
C = US
E = Your Email
```

OK, now that you have your PFX, you can generate a CAT for your modded driver and sing it (you will need the latest Windows Driver Kit)
```
Re-generate a new CAT with Inf2Cat with:
Inf2Cat /driver:<path_to_folder_with_INF_&_Files> /os:Vista_X86,Vista_X64,Server2008_X86,Server2008_X64,7_X86,7_X64,Server8_X64,8_X86,8_X64,Server6_3_X64,6_3_X86,6_3_X64
```
*	Sign the new CAT with your PFX
	signtool sign `/f <filename>.pfx /p <password> "<path_to_folder>\nv_disp.cat"`
*	Timesamp your CAT file
	`signtool timestamp /t http://timestamp.verisign.com/scripts/timstamp.dll "<path_to_folder>\nv_disp.cat"`
* 	 Now what you need to do, is get the cert from your PFX, install it in the Trusted Root Cert. Auth. and get the reg from this to give to users to apply


Telemetry
======

All information regarding to the driver bundled telemetry can be found under the `/Telemetry & Crap free` folder. 

It's not necessary to block telemetry with your firewall, since you can manually opt-out, install a 'crap free' version or remove the folders/services manually. It's also unclear if blocking with firewall is effective since the data are tunneled transmitted + encrypted [needs confirmation]. 



Release
======

The latest Vulkan Runtimes and de-bloated Drivers can be found under the [release page](https://github.com/CHEF-KOCH/nVidia-modded-Inf/releases). 


**Do not request new drivers/runtimes or .inf via the GitHub issue ticket, it will result in a permanent project ban!** 



## Acknowledgements and References
* [DDU Source Code](https://github.com/Wagnard/display-drivers-uninstaller)
* [Nvidia INF driver modding](http://forums.guru3d.com/showthread.php?t=377158)
* [LaptopVideo2Go](https://laptopvideo2go.com/)
* [GeForce Driver Installation Guide A guide to ensure your drivers are installed properly.](https://forums.geforce.com/default/topic/467215/geforce-driver-installation-guide-a-guide-to-ensure-your-drivers-are-installed-properly-/)
* [Windows 10 FAQ and Driver installation tips](https://forums.geforce.com/default/topic/862424/geforce-drivers/windows-10-faq-and-driver-installation-tips-/)
* [PC Gaming Wiki](https://pcgamingwiki.com/wiki/Home)
* [PCI ID Project](http://pci-ids.ucw.cz/pci.ids)

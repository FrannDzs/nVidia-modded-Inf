<p align="center">
  <img src="https://raw.githubusercontent.com/CHEF-KOCH/nVidia-modded-Inf/master/.github/Pictures/geforce.png" width="350"/>
  <img src="https://raw.githubusercontent.com/CHEF-KOCH/nVidia-modded-Inf/master/.github/Pictures/inf%20mod.png" width="350"/>
</p>

#### nVidia modded Inf project was created 2017 by CHEF-KOCH and is under GNU GENERAL PUBLIC LICENSE v3.

The project is _unofficial_ and not in any relationship or supported by [nVidia Cooperation](https://www.nVidia.com/en-us/about-nVidia/).

This project only support x64 Windows 10 versions, if you like to see x86 [ask nVidia to extend the support](https://www.anandtech.com/show/12191/nVidia-to-cease-driver-development-for-32bit-operating-systems).

[![GitHub](https://img.shields.io/github/license/CHEF-KOCH/nVidia-modded-Inf.svg?label=Project%20license&style=popout)](https://github.com/CHEF-KOCH/nVidia-modded-Inf/blob/master/LICENSE)
[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/fold_left.svg?style=social&label=Follow%20%40CHEF-KOCH)](https://twitter.com/CKsTechNews)
![GitHub All Releases](https://img.shields.io/github/downloads/CHEF-KOCH/nVidia-modded-Inf/total.svg?style=popout)
[![Discord](https://discordapp.com/api/guilds/418256415874875402/widget.png)](https://discord.me/CHEF-KOCH)


What is a modded INF?
===================

All drivers come with an "Installation INF(ormation) file". This tells the Windows internal installer how to install the driver. The INF has the instructions to what files to copy and where. It will also setup settings to install with. The INF-file itself contains a list of supported products (hardware/software/OS) that it will check and install for.

nVidia provides UDA (Unified Driver Architecture) where the driver should work for all their released GPUs. So the driver itself will support all GPUs, but the INF the driver comes with will only support a selected set of GPUs.

nVidia by default don't support laptop GPUs with beta and WHQL driver updates on their server. This is left up to the OEM to organize. I assume nVidia must charge to have an OEM driver made or be included, as they are very rear for OEM to actually update a video driver. So an OEM driver has specific instructions for that laptop (ie model specific) and will only work with a select few laptops.

For example a Toshiba OEM driver with a Toshiba INF (nvts.inf) will only work with the models included in that INF.

Modded drivers will NEVER transform your GPU to another one and will NEVER add features that you do not already have.


**Reasons for modding**
* New driver features tests.
* You like to test newer driver(s) which are no longer supported.
* It could be used to force installation of newer drivers on OEM locked GPUs.
* You need an older driver that is not officially supported for your GPU because you have a specific application that is broken in newer ones and you cannot wait for a fix.
* Security reasons, you should ALWAYS use the latest driver (if possible) due to [possible driver flaws](https://www.bleepingcomputer.com/news/security/nvidia-patches-high-severity-windows-gpu-display-driver-flaws/)


**Keep in mind**:

> Fermi GPUs (400 & 500 series) as from 396+ driver are official no longer supported! Same goes for [700M and 800M GPU's](https://nvidia.custhelp.com/app/answers/detail/a_id/4779). Latest official Fermi driver is Quadro 392.58, [Windows 7/8](http://us.download.nvidia.com/Windows/Quadro_Certified/392.58/392.58-quadro-desktop-notebook-win8-win7-64bit-international-whql.exe) & [Windows 10](http://us.download.nvidia.com/Windows/Quadro_Certified/392.58/392.58-quadro-desktop-notebook-win10-64bit-international-whql.exe) (the driver works for all GTX 460 series up to GTX 1080 Ti [via Inf. mod]).



SD, CD, GRD, DCH or Standard drivers?
===================

Short answer:
* "Standard" packages are those that do not require the DCH driver components. DCH represents UWD which you can install via the Windows Store or manually.
* Standard is the "old" way which you (for now) should prefer since UWD drivers aren't tweakable (in terms of mods) compared to the standard (legacy) drivers.
* "DCH" (Declarative, Componentized, Hardware Support Apps) refers to new packages pre-installed by OEMs implementing the Microsoft Universal Driver paradigm.
* DCH drivers cannot be installed over a standard system, and Standard drivers cannot be installed over a DCH system.
* To confirm the type of system you have, locate Driver Type under the System Information menu in the nVidia Control Panel.


##### Detailed Answer

DCH is a collaboration platform supporting the process of commercial forecasting Demand Collaboration Hub (DCH) is a collaboration platform that enables all members of your Sales organization, at the various hierarchical levels, to submit, consolidate and validate their periodic commercial forecast. DCH is fully configurable, allowing you to model the workflow and segment the data between users, in relation to their level of responsibility, to configure your editing form, by selecting and publishing the information that are relevant for your sales organization, to enter commercial forecast at various level of aggregation, with automatic splitting of edited quantities to the level of maximum detail. DCH is part of the SO99+ (Service Optimizer 99+) product suite and more specifically it is complementary to its statistical forecasting functionality, since the statistical forecast may be used as a guidance to support the Sales organization to provide more reliable figures. To support mobility, DCH is available on the web or from any mobile device that your Sales organization may adopt.

##### Update 13.12.2019

[Windows 10 will get DCH by default](https://www.nvidia.com/en-us/geforce/forums/game-ready-drivers/13/332096/geforce-44166-game-ready-driver-feedback-thread-re/2339006/) (via WUS and NVIDIA website) (_Windows 7 is not affected_). This means "standards" driver are been fully replaced by DCH.


Difference between INF(s) - Standard Vs. DCH
===================

nVidia decided to make a clear cut with the "Super" cards, this basically means the infs got "separated" into two versions v7 - which represents DCH (see above what DCH drivers are) and v6 (old) are the normal "standard" drivers. The versions numbering might be changed completely next year (unclear at this point). 


What does this mean for you as user? 

Basically nothing, except that you need at least Windows 10 Build 17098 (19H2)+ in order to run DCH modded drivers/infs, theoretically the infs are working on lower builds too but due to performance problems I do not recommended it (WDDM 2.7 was introduced in later drivers/Windows versions). However, keep in mind that (because I often get asked) that it's not possible to combine Standard and DCH Infs ("All-in-one inf") because DCH setups are different from the normal ones.

The telemetry is disabled in any of the modded DHC infs. In case you like to enable it you have to manually set it to "1" within the inf files before you install your desired driver.



Which driver should I install - Standad, DCH ...?
===================

##### Official nVidia recommendation
* SD (Studio Driver, might replaces the "Creators Driver") = For **content creators, video editing, animation or graphic design**, use this driver.
* CD (Creators Driver) = Same like SD, it might get replaced with the Studio Driver version (re-label).
* GRD (Game Ready Driver) = For **gamers** which need the latest patches & DLCs. If you are gamer & creator, use this driver.
* Standard GRD Driver = The normal oldschool driver for **Windows Home/Pro/Enterprise/LTSC** which want to game, use this driver.
* DCH (Declarative, Componentized, Hardware Support Apps) = For **Windows S, Core users or user with a Windows Store which prefering to get the latest NVCP over the Store**, use this driver.


##### My own recommendation
* Stick with the **normal (GR [GRD]) driver** the rest is more or less marketing/pr with no real benefits. The driver packages are almost identical (except the DCH package). If you Windows version is a "special case" like the S/Core version then use the DCH version. 


How-to remove old nVidia drivers
===================

* Extract Display Driver Uninstaller (DDU) and start the program, boot into "safe mode" (you can do this manually or within the given DDU option) and let DDU auto-clean and restart the OS automatically for you. You do not need to uninstall the driver or any package via Windows own uninstaller program first (that's the whole point using DDU). Keep in mind that **DDU should only be used in case you get troubles while uninstalling/installing the driver with nVidia's own Setup**, it's not recommend and needed to use DDU as 'normal' driver removal procedure. nVidia's own setup routine usually does the job just fine, however in some cases in can help to remove leftovers which _might_ cause trouble.
* After you rebooted you install the (modded/repack) nVidia driver, if the driver isn't digital signed you need to do it yourself or disable Windows driver signature enforcement.

The official DDU guide can be found over [here](https://www.wagnardsoft.com/content/ddu-guide-tutorial).



Modded Inf Driver installation
===================

* Download and extract the Driver (download from official source) - wait until the installer has unzipped the files e.g. to `C:\nVidia`.
* Search for e.g. "nv_disp.cat" (or corresponding inf-file) in the 'Display.Driver Folder'.
* Follow the Video or the written instruction to install the certificate manually (optional).
* Now you can install all my modded drivers, without disabling 'driver signature enforcement'.



How to show current driver branch?!
===================

* Download [nVidia Inspector](https://www.softpedia.com/get/System/System-Info/nVidia-Inspector.shtml)
* Check the Overview Window under "Driver version" you see the installed driver branch.



Troubleshoot - Disable Driver Signatures
===================

Check the [current secure boot status](https://docs.microsoft.com/en-us/powershell/module/secureboot/confirm-securebootuefi?view=win10-ps) (optional), which gives you `true` or `false` (enabled/disabled) back:

```

Powershell confirm-SecureBootUEFI

```


Before you install unsigned drivers, you have to manually set [those parameters](http://acer.custhelp.com/app/answers/detail/a_id/38289/~/windows-10%3A-disable-signed-driver-enforcement) via administrative command prompt to [turn secure boot](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/disabling-secure-boot) off:

```
bcdedit -set loadoptions DISABLE_INTEGRITY_CHECKS

bcdedit -set testsigning ON

shutdown.exe /r /o
```


After you're finished installing the unsigned driver:

```
bcdedit -set loadoptions ENABLE_INTEGRITY_CHECKS

bcdedit -set {globalsettings} advancedoptions true

bcdedit -set TESTSIGNING OFF
```


After executing the mentioned commands you need to reboot Windows 10 in order to apply the changes. Some (if not all) new laptops have no options to turn [secure boot](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-secure-boot) off.



How-to sign your own modded driver?
===================

Download and install (or use the portable) [SelfCert](https://www.pluralsight.com/blog/software-development/selfcert-create-a-self-signed-certificate-interactively-gui-or-programmatically-in-net).

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



What an "inf mod" can't provide
===================

- [x] Adding support for [legacy GPU's](https://www.nvidia.com/object/IO_32667.html)  (see EOL) because nVidia removed (within the source code) support for it and there is no _patch_ which can undo or manipulate it.
- [x] I'm not permitted to upload modified .dll files so please do not ask for "patch xyz". I _consider_ to provide bunch of offset patches I use, without any tool or information how you add these patches because it violates nVidia TOS (it's not _my fault_).



Telemetry
===================

All information regarding driver bundled telemetry can be found under the `/Telemetry` folder.

It's not necessary to block telemetry with your firewall, since you can manually opt-out or install a '[crap free](https://github.com/CHEF-KOCH/nVidia-modded-Inf/releases)' version and you also can remove the unneeded folders/services manually.


The Guru3d user [uKER](https://forums.guru3d.com/members/uker.96766/) programmed a little utility called [NVSlimmer](https://forums.guru3d.com/threads/nVidia-driver-slimming-utility.423072/) which allows you (via GUI) to remove the _unneeded_ folders/features - it's basically the same as doing it via a batch/cmd but with an simple interface to allow you to manually select all folders based on your own 'removal needs', the program includes also an integrated required list in order to warn user what is really necessary to keep in order to use the driver.

Another program (rip-off from NVSlimmer) called "NVCleanstall" can be found in the [TechPowerUP forums](https://www.techpowerup.com/forums/threads/nvcleanstall-clean-installer-for-nVidia-drivers-alpha.249085/).



Driver Release Overview
===================

* [![nVidia stable](https://img.shields.io/github/release/CHEF-KOCH/nVidia-modded-Inf.svg?label=Latest%20nVidia%20stable&style=popout)](https://github.com/CHEF-KOCH/nVidia-modded-Inf/releases/latest)

* [![nVidia beta](https://img.shields.io/github/release-pre/CHEF-KOCH/nVidia-modded-Inf.svg?label=Latest%20nVidia%20beta&style=popout)](https://github.com/CHEF-KOCH/nVidia-modded-Inf/tags)

* Latest nVidia PhysX System Software: [9.19.0218](http://us.download.nVidia.com/Windows/9.19.0218/PhysX-9.19.0218-SystemSoftware.exe)
* Latest nVidia GeForce Experience ([Changelog](https://www.geforce.com/geforce-experience/download)): [3.20.1.57 Stable](https://de.download.nvidia.com/GFE/GFEClient/3.20.1.57/GeForce_Experience_v3.20.1.57.exe) & [Beta (old) 3.18.0.102](https://de.download.nVidia.com/GFE/GFEClient/3.18.0.102/GeForce_Experience_Beta_v3.18.0.102.exe)



## Acknowledgement & References
* [Reshade filters (nvidia.com)](https://www.nvidia.com/en-us/geforce/news/geforce-gtx-16-series-super-game-ready-driver/)
* [DDU Source Code (github.com/Wagnard)](https://github.com/Wagnard/display-drivers-uninstaller)
* [GeForce Driver Installation Guide A guide to ensure your drivers are installed properly (forums.geforce.com)](https://forums.geforce.com/default/topic/467215/geforce-driver-installation-guide-a-guide-to-ensure-your-drivers-are-installed-properly-/)
* [Install nVidia drivers on macOS the easy way (github.com)](https://github.com/Benjamin-Dobell/nVidia-update)
* [LaptopVideo2Go (laptopvideo2go.com)](https://laptopvideo2go.com/)
* [Official nVidia Display Driver Feedback Page (surveys.nvidia.com)](https://surveys.nVidia.com/index.jsp?pi=6e7ea6bb4a02641fa8f07694a40f8ac6)
* [PC Gaming Wiki (pcgamingwiki.com)](https://pcgamingwiki.com/wiki/Home)
* [PCI ID Project (pci-ids.ucw.cz)](http://pci-ids.ucw.cz/pci.ids)
* [Windows 10 FAQ and Driver installation tips (forums.geforce.com)](https://forums.geforce.com/default/topic/862424/geforce-drivers/windows-10-faq-and-driver-installation-tips-/)
* [nVidia INF driver modding (forums.guru3d.com)](http://forums.guru3d.com/showthread.php?t=377158)
* [G-SYNC Compatible Testing, Phase 1 Complete: Only 5% of Adaptive-Sync Monitors Made The Cut (nvidia.com)](https://www.nvidia.com/en-us/geforce/news/g-sync-compatible-validation/)

## Debugging & Official Driver Feedback Websites
* [NVIDIA Display Driver Feedback (bug reporting)](https://forms.gle/kJ9Bqcaicvjb82SdA) - **Use it to report your bugs!**
* [Capturing application crash or TDR dump files on Windows](https://nvidia.custhelp.com/app/answers/detail/a_id/3335) 
* [How to enable nVidia Graphics Driver and GeForce Experience installer logging (nvidia.custhelp.com)](https://nvidia.custhelp.com/app/answers/detail/a_id/3171/)

## Unofficial NVIDIA patches
* [Driver patch for enabling unlimited NVENC sessions (old) (github.com)](https://github.com/Matviy/nVidia-NVENC-multi-session-patch)
* [NvencSessionLimitBump (github.com)](https://github.com/jantenhove/NvencSessionLimitBump)
* [WhateverGreen (github.com)](https://github.com/acidanthera/WhateverGreen)
* [Wine patches (github.com)](https://github.com/SveSop/wine_patches)
* [nVidia kvm patcher (github.com)](https://github.com/sk1080/nVidia-kvm-patcher)
* [nVidia patch to remove restriction on maximum number of simultaneous NVENC video encoding session (github.com)](https://github.com/keylase/nVidia-patch)
* [purge-wrangler (github.com)](https://github.com/mayankk2308/purge-wrangler)

## Unofficial driver updater
* [nVidia Update PowerShell Script (github.com)](https://github.com/lord-carlos/nVidia-update)

## Bios
* [Maxwell Bios Tweaker for edit nVidia GTX 9XX bios (github.com)](https://github.com/richardblynd/maxwellbiostweaker)
* [VGA and BIOS rom font extraction (github.com)](https://github.com/spacerace/romfont)

## EOL
* CRD (Studio Drivers) are re-labeled to NSD
* [End of Driver Support for Quadro Kepler-series Notebook Products (April 30, 2020)](https://nvidia.custhelp.com/app/answers/detail/a_id/4788)
* [Support Plan for 3DVision Products (nvidia.custhelp.com)](https://nvidia.custhelp.com/app/answers/detail/a_id/4781)
* [Support Plan for Kepler-series GeForce GPUs for notebooks (nvidia.custhelp.com)](https://nvidia.custhelp.com/app/answers/detail/a_id/4779)

## NVIDIA market share
* [GPU shipments in Q3’19 (jonpeddie.com)](https://www.jonpeddie.com/press-releases/sharp-rise-in-global-gpu-shipments-in-q319-reports-jon-peddie-research)

- [Display.Driver](#displaydriver)
- [Display.NView](#displaynview)
- [Display.Optimus](#displayoptimus)
- [Display.Update](#displayupdate)
- [GFExperience](#gfexperience)
- [HDAudio](#hdaudio)
- [MSVCRT](#msvcrt)
- [NGXCore](#ngxcore)
- [nodejs](#nodejs)
- [NvAbHub](#nvabhub)
- [NvBackend](#nvbackend)
- [NvCamera](#nvcamera)
- [NvContainer](#nvcontainer)
- [NVI2](#nvi2)
- [NvTelemetry](#nvtelemetry)
- [NvVAD](#nvvad)
- [NvvHCI](#nvvhci)
- [PhysX](#physx)
- [PPC](#ppc)
- [ShadowPlay](#shadowplay)
- [ShieldWirelessController](#shieldwirelesscontroller)
- [Update.Core](#updatecore)
- [EULA.txt](#eulatxt)
- [license.txt](#licensetxt)
- [ListDevices.txt](#listdevicestxt)
- [setup.cfg](#setupcfg)
- [setup.exe](#setupexe)
- [Where does GeForce Experience download the drivers?](#where-does-geforce-experience-download-the-drivers)


## Display.Driver

The folder contains the driver. The folder should never never be removed.

## Display.NView

[nView Desktop Management Software](https://www.nvidia.com/en-us/design-visualization/solutions/nview-display/) provides support for multi-monitor setups which basically [tells Windows how to deal with multiple monitors](https://nvidia.custhelp.com/app/answers/detail/a_id/3052/~/nview-desktop-manager-software-users-guide). NView is deprecated. 


## Display.Optimus

[Optimus](https://www.nvidia.com/object/optimus_technology.html) is optional and original designed to power manage your notebook.


## Display.Update

This folder contains the Update.Core service which is used to update your graphic driver in case a new release is avbl. It's also used by GFE in order to notify you about the update itself. This is optional.


## GFExperience

[GeForce Experience](https://www.nvidia.com/en-us/geforce/geforce-experience/) (GFE) is optional and will be installed by default. 


GFExperience.NvStreamSrv

The streaming service is same as GFE itself optional, the folder itself holds the server files which is created by [ShadowPlay](https://www.nvidia.com/en-us/geforce/geforce-experience/shadowplay/) to start and stop the recording/streaming.


## HDAudio

This is _semi-optional_, the folder includes the driver files for [nVidia's HD Audio](https://www.nvidia.com/object/IO_27962.html) which is required in case you use HDMI/Audio output directly from/to your monitor(s). Some features explicitly need the driver or checking if the driver is installed but in normal situations it's not required to install the driver. 

In the repack versions the HD Audio driver is included, it doesn't waste much space on your HDD and you could manually enable/disable it whenever you need it in the Windows Audio Manager.


## MSVCRT

Microsoft Windows library (short: MSVCRT) folders contains the shared libraries which are required for several services like e.g. GFE, if you already have the MSVCRT installed you don't need them. 


## NGXCore

[NVIDIA NGX Technology](https://developer.nvidia.com/rtx/ngx) folder is optional and provides AI-based features that accelerate and enhance graphics, photos imaging and video processing directly into some applications. Unless you really need/work with it you usually don't need it, if you're unsure check the [documentation](https://docs.nvidia.com/rtx/ngx/programming-guide/index.html).

## nodejs

[Node.js](https://nodejs.org/) is a cross-platform JavaScript run-time environment that executes JavaScript code outside of a browser, this is required for several functions like e.g. streaming, update checks etc. If you don't use GFE and other services you don't need the folder.


## NvAbHub

It's a plugin and optional. 


## NvBackend

The nVidia Backend folder provides dll's for several functions, update check, battery checks 


## NvCamera

[nVidia Ansel](https://www.geforce.com/hardware/technology/ansel) is already deprecated and optional. Some games still use it so you can make the decision if you need it or not based on which games you have installed or you plan to install e.g. WatchDogs has nVidia Ansel support. Ansel itself is known to cause some FPS issues (if enabled) in several games and under several conditions.
 

## NvContainer

The [Container process](https://www.howtogeek.com/343120/what-are-all-those-nvidia-processes-running-in-the-background/) and service is optional but is required for several integrated functions like GFE (e.g. the Overlay) to function probably. 


## NVI2

NVi2 provides parts of the setup installer code and should not be removed because you will not be able to install the driver without it.


## NvTelemetry

Everyone's necessary evil, some people like it other want to get rid of it. The Telemetry folder is optional and can be removed. You should consider if you want to help nVidia to improve the driver by sending feedback or not. 


## NvVAD

Contains a driver `NVIDIA Virtual Audio Device (Wave Extensible) (WDM)` and is optional, if you don't have/use it you can remove the folder.


## NvvHCI

NVVHCI Enumerator (nvidia Virtual USB Host Controller driver) is an optional process and the folder can be removed. The service is only needed to get the USB-Port on your Shield device working. 



## PhysX

nVidia's [PhysX](https://www.geforce.com/hardware/technology/physx) is an open-source real-time physics engine middleware SDK developed as a part of Nvidia GameWorks software suite.


## PPC

Same as NvVAD the folder contains a driver, in this case `NVIDIA USB Type-C Port Policy Controller` which is optional. 


## ShadowPlay

The folder is optional and contains [ShadowPlay](https://www.nvidia.com/en-us/geforce/geforce-experience/shadowplay/) components. The service is depending on GFE and GFExperience.NvStreamSrv in order to record/stream your game. An open-source alternative to it is [OBS Studio](https://obsproject.com/) which includes also the nVidia SDK to use nVidia NVENC (nVidia Encoder) which is similar to ShadowPlay.


## ShieldWirelessController

As the name already says, the folder contains the optional Wireless Controller driver.  If you don't need/use it you can remove the folder. 


## Update.Core

The folder is optional and only required in case you use the integrated driver update mechanism. 


## EULA.txt

[End-user license agreement](https://en.wikipedia.org/wiki/End-user_license_agreement) (EULA) file.

## license.txt

The [license](https://en.wikipedia.org/wiki/License) file.


## ListDevices.txt

The devices list is checked by the setup.exe to see if your hardware is compatible or not.


## setup.cfg

The setup.cfg basically tells the setup.exe what to look for and what to install. You theoretically can manipulate it to cheat around several limitations or to simply tell the setup to exclude several things from been installed. If you repack a driver you often see another file `setup.cfg.bak` which is the original (untouched) file.


## setup.exe

The Setup which is required to install the driver and it's components. `EULA.txt`, `license.txt`, `ListDevices.txt` & `setup.cfg` is required and should not be removed because the setup.exe checks it, without it the setup will not function properly. 



## Where does GeForce Experience download the drivers?
```
C:\ProgramData\NVIDIA Corporation\NetService 
C:\ProgramData\NVIDIA\Updatus\DownloadManager
C:\ProgramData\NVIDIA Corporation\GeForce Experience\Update
```
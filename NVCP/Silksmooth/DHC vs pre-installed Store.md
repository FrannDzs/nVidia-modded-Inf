## Why install DCH if the official NVidia Control Panel comes pre-installed?

There are several reasons, some Windows versions ([WinS](https://en.wikipedia.org/wiki/Windows_10_editions)/Chinese) comes without any pre-installed driver and the OEM can choose to use the DCH ones to force people stay up-2-date since all Store Apps (by default) getting updated on a regular basis. This basically means the main reason why DCH drivers exist is because of those editions since they _force_ any users to use UWP apps instead of the old Win32 apps. 


## How do I use the nVidia Control Panel app in Home/Pro/Enterprise Editions?

I see no reason to use it but you need a) DCH drivers (uninstall the old driver and all components first) and b) you need an official [App Installer](https://www.microsoft.com/en-us/p/app-installer/9nblggh4nns1) in order to install the application/app which allows you to install the nVidia Control Panel manually (if you choose to not use it directly from the MS store). 

## Manual installation

* [Microsoft App Installer ](https://www.microsoft.com/store/productId/9nblggh4nns1)
* [DCH NVIDIA Control Panel 8.1.950.0 x64](https://mega.nz/#!wRFUBYZR!2H8Y5RsC1J776_gZr8JZMQOh0tLe4_I5448ZA-cPsac)
* Install it by double clicking on _NVIDIACorp.NVIDIAControlPanel_8.1.950.0_x64__56jybvy8sckqj.Appx_ and the App Installer will automatically add it. 

## I can't install the nVidia Control panel via MS App Store directly - what to do?

There are multiple reasons, the old driver and DCH are incompatible to each other, you need to install a DCH driver first otherwise you see [this](https://i.imgur.com/r2RI6fT.jpg) error. Another reason is that the MS Store itself checks on which Windows version you are and blocks it. I highly recommend to go with the manual installation method described above.

However there is a registry tweak in order to bypass MS own check/error (Supported NVIDIA Driver is not installed on your system):
```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\nvlddmkm\FTS]
"EnableRID69527"=dword:00000001
```

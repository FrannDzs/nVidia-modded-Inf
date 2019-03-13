## Reason to update the Firmware

* Fix blank screens problems in relationship with DisplayPort 1.3 / 1.4 
* Update your GPU BIOS to stay up2date
* Allow up-/downgrades for fix _other_ problems

## How do I list the current GOP/BIOS?

* Via `nvflash64 -il (or -i0) -v`


There are basically two ways to update your nVidia/AMD graphics card firmware GOP
---------------

1. (_recommend_) Official updater utility
   * Download the official [NVIDIA Graphics Firmware Update Tool for DisplayPort 1.3 and 1.4 Displays utility](https://www.nvidia.com/object/nv-uefi-update-x64.html)
   * Execute the program, it will automatically check your current OS/Firmware and flash a newer version (if needed).


2. (_advance users_) Via Win-RAID Forum GOPUpd utility (nvflash) which also works for AMD Users
   Download `Win-RAID Forum GOPUpd utility` (listed under `/Tools`, background infos are [here](https://www.win-raid.com/t892f16-AMD-and-Nvidia-GOP-update-No-requests-DIY.html)) it includes the source code and all you need to quickly update your GOP.
   **Make a backup of your current BIOS!** you can do this via `nvflash64.exe --save backup.rom` (AMD users need to use `AtiFlash.exe -s 0 backup.rom`) additional parameters can be found via `nvflash64.exe -?` or `atiflash -?`. [GPU-Z can backup your BIOS too](https://www.techpowerup.com/download/gpu-z/).
   Drag & drop your BIOS ROM into `GOPUpd.bat` which then will list information about your GPU bios and list GOP version. If you#re not on the latest version you can try to find a BIOS update and flash it via nvflash64.exe manually.


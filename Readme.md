### nVidia modded Inf project created 2017 by CHEF-KOCH under GNU GENERAL PUBLIC LICENSE v3.


What is a modded INF?
===================

All drivers come with an "Installation INF(ormation) file". This tells the installer how to install the driver. The INF has the instructions to what files to copy and where. It will also setup settings to install with. The INF also has a list of products that it will install for.

nVidia provides UDA (Unified Driver Architecture) where the driver should work for all their released GPUs. So the driver itself will support ALL GPUs, but the INF the driver comes with will only support a selected set of GPU

nVidia by default don't support laptop GPUs with beta and WHQL driver updates on their server. This is left up to the OEM to organize. I assume nVidia must charge to have an OEM driver made or be included, as they are very rear for OEM to actually update a video driver. So an OEM driver has specific instructions for that laptop (ie model specific) and will only work with a select few laptops.

For example a Toshiba OEM driver with a toshiba INF (nvts.inf) will only work with the models included in that INF.




Easy installation:
===================


* Download and extract the Driver (download from official source) - wait until the installer has unzipped the files e.g. to C:\Nvidia
* Search "nv_disp.cat" (or corresponding file) in 'Display.Driver Folder'
* Follow the Video instruction to install the certificate
* Now you can install all my modded drivers, without disabling 'driver signature enforcement' in Windows.



ToDo:
======


* Add video
* Add more instruction and project details in Readme.md 
* Mention nvFlash and DDU
* Add manual 'create own inf' section
* Add 'how to install driver manually' + video?
* Add devide Id list



Research and tools:
===================

* https://github.com/Wagnard/display-drivers-uninstaller
* http://forums.guru3d.com/showthread.php?t=377158
* https://laptopvideo2go.com/
* 
* 
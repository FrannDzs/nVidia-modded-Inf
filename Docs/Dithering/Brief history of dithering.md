### Overview

Dithering help us to fight against [color banding](https://en.wikipedia.org/wiki/Colour_banding), the main question is (or was) if it affects the gaming performance, this seems to be answered once and for all now. 

Most newer TN panels above 120 Hz did suffered from color banding, especially if the gamma curve was get above 2.2 (e.g. in madVR).


### History

Back in Dec. 2018 a forum member called "Guzz" unlocked dithering under Windows with nVidia drivers via a registry hack, the original post can be found [here](https://forums.geforce.com/default/topic/1082681/geforce-drivers/is-it-possible-to-quot-port-quot-dithering-from-nvidia-x-server-to-geforce-driver-/post/5934577/#5934577). The registry "tweak" still works even in newer Windows versions and newer drivers (with some modifications).


### FPS impact

The short answer is that [enabling dithering has no impact on gaming performance](https://www.youtube.com/watch?v=ot3TWFtWl1M), so it is unclear why nVidia and Microsoft are not going to enable the option (by default) for e.g. 1440p 144-165Hz G-Sync TN monitor (the ones which are most affected by color banding). AMD GPU drivers have such an option to enable/disable dithering since many years. 


### Problems with Windows

It seems Microsoft does not want such an option for nVidia drivers (needs confirmation), you see that several (stable) Windows Builds acting differently when it comes to the unlocked dithering topic. Windows 1709 - 1803 had several improvements for AMD users, especially for the Ryzen generation. 

Broken (or problematic) implementations with Windows Build 1809 - 1903, several people reporting massive problems whenever the tweak was enabled. 


### Windows 1903+ 

These builds seems have changed a lot, Windows tries to overwrite several settings after xyz minutes, you can observe such behavior via regmon. The issue seems to return after a shutdown and your manually configured ICC profiles become broken again.


### Linux

Linux does not have such a dithering problem, even with the proprietary drivers. There are a lot other option which I could mention which are working fine under Linux. 


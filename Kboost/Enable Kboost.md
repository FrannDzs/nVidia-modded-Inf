### Does EVGA KBoost work on non EVGA graphics cards?

No, it will be grayed out.  My Titan X pascals can use Precision; but, K-boost is not an option. K-boost just runs the GPU at full power even when idle.


#### Requirements

1. MSI Afterburner + [EVGA Precision X Skin](https://youtu.be/x230aMQBwxg)
2. Nirsoft's [devmanview](http://www.nirsoft.net/utils/device_manager_view.html) 
3. Find the Name of your Active Nvidia Graphics Card "Nvidia Geforce GTX xxx" 
   
Open a Console/Powershell or whatever shell with the directory you extracted devmanview into.

Type (replace graphic card name with the one you own):

```bash
devmanview /disable_enable "NVIDIA GeForce GTX 970"
```

The Driver will restart and MSI Afterburner should jump to the highest clocks and Voltage immediately. To disable it just select KBoost again cancel the restart advice and once more restart the driver the clocks and voltage should fall back to normal.


### Alternative registry method

Use "regedit", search after Card ID e.g "4D36E968-E325-11CE-BFC1-08002BE10318"
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Video\{*gfx card ID*}\0000 or with IGPU 0001

```reg
; Add
"PowerMizerEnable"=dword:00000001 [1 for on, 0 for off]
"PerfLevelSrc"=dword:00002222 [or 3322 for different battery and AC settings] ... 22 is for fixed setting and 33 for adaptive
"PowerMizerLevel"=dword:00000001 [1 = high, 2 = med, 3 =low] ... this is the setting for when using battery
"PowerMizerLevelAC"=dword:00000001 [1 = high, 2 = med, 3 =low] ... this is the setting for when using AC
```

_Optional_ for temperature safety underclocking override:
```reg
"EnableCoreSlowdown"=dword:00000001
"EnableMClkSlowdown"=dword:00000001
"EnableNVClkSlowdown"=dword:00000001
```


Credits:
* Cru_N_cher
* Cyris
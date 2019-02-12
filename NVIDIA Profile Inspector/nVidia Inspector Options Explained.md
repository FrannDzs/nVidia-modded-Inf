## What is NVIDIA Profile Inspector?

[Nvidia Profile Inspector (NPI)](https://github.com/Orbmu2k/nvidiaProfileInspector/releases) is a third-party tool created by Orbmu2k for pulling up and editing application profiles within the Nvidia display driver(s). It works much like the Manage 3D settings page in the Nvidia Control Panel (NVCP), but goes more in-depth and exposes settings and offers functionality not available through the normal control panel.


## Compatibility

* **Ambient Occlusion compatibility**

Basically allows [HBAO+](https://www.geforce.com/hardware/technology/hbao-plus) to work with any given game.


* **Antialiasing Compatibility**

Allows various forms of [anti-aliasing](https://www.geforce.com/whats-new/guides/aa-af-guide) to work with any given DirectX 9 game.

* **Antialiasing Compatibility (DX1x)**

Allows various forms of anti-aliasing to work with DirectX 10/11/12 games. Often restricted to MSAA and generally sees little use due to its limited capability.

* **Antialiasing fix**

Avoid black edges in some games while using [MSAA](https://www.geforce.com/hardware/technology/mfaa/technology). Related to Team Fortress 2 and a few other games as well, where it is enabled by default.

* **SLI compatibility bits**

Allows [SLI](https://www.geforce.com/whats-new/guides/introduction-to-sli-technology-guide) to work in any given DirectX 9 game.

* **SLI compatibility (DX 10 + DX 11)**

Allows SLI to work in any given DirectX 10/11 game.

* **SLI compatibility (DX 12)**

Allows SLI to work in any given DirectX 12 game.


## Sync and Refresh

* **Flip Indicator**

Enables an on-screen display of frames presented using flip model.
  
* **Frame Rate Limiter**

The built-in frame rate limiter of the Nvidia display drivers introduces 2+ frames of delay, while RTSS (and possibly other alternatives) only introduces 1 frame of delay. A better frame rate limiter is [RTSS](https://www.guru3d.com/files-details/rtss-rivatuner-statistics-server-download.html). 

* **Frame Rate Limiter Mode**

Controls what mode of the frame rate limiter will be used.
  
* **GSYNC - Application Mode**

Controls whether the G-Sync feature will be active in fullscreen only, or in windowed mode as well.

* **GSYNC - Application Requested State** 

If you know what this setting does, please add a description here.

* **GSYNC - Application State**

Selects the technique used to control the refresh policy of an attached monitor.
- [x] Allow enables the use of G-Sync, and syncronizes monitor refresh rate to GPUs render target.
- [x] Force off and Disallow disables the use of G-Sync.
- [x] Fixed Refresh Rate is the traditional fixed refresh rate monitor technology.
- [x] Ultra Low Motion Blur (ULMB) uses back light pulsing at a fixed refresh rate to minimize blur.

It is highly recommended to change this using the Nvidia Control Panel > Manage 3D Settings > Monitor Technology instead to properly configured this and related parameters.

* **GSYNC - Global Feature**

Toggles the global G-Sync functionality. It is recommended to change this using the Nvidia Control Panel > Set up G-SYNC instead to properly configured this and related parameters.

* **GSYNC - Global Mode** 

Controls whether the G-Sync feature will be active globally in fullscreen only, or in windowed mode as well.

* **GSYNC - Indicator Overlay** 

Enables a semi-transparent on-screen status indicator of when G-Sync is being used. If G-Sync is not being used, the indicator is not shown at all.

* **Maximum pre-rendered frames**

Controls how many frames the CPU can prepare ahead of the frame currently being drawn by the GPU. Increasing this can result in smoother gameplay at lower frame rates, at the cost of additional input delay.[3] This setting does not apply to SLI configurations.
- [x] Default is Use the 3D application setting, and it is recommended not to go above 3. Values of 1 and 2 will help reduce input latency in exchange for greater CPU usage.[4]
- [x] When Vsync is set to 1/2 Refresh Rate, a value of 1 is essentially required due to the introduced input latency.

* **Prefered Refreshrate** 

Controls the refresh rate override of the display drivers for games running in exclusive fullscreen mode. This also dictates the upper limit of the G-Sync range, as G-Sync will go inactive and the screen will start to tear at frame rates above the configured refresh rate, or V-Sync will kick in and sync the frame rate to the refresh rate if enabled.
- [x] Highest available - Overrides the refresh rate of the exclusive fullscreen game to whatever is the highest available on the monitor. This setting is automatically used when G-Sync is enabled. Note that this override might not work for all games, in which case an alternative such as Special K might be needed.
- [x] Use the 3D application setting / Application-controlled - Uses the refresh rate as requested by the application. If using G-Sync, frame rates above the requested refresh rate will result in screen tearing as G-Sync will go inactive, or V-Sync synchronizing the frame rate to the refresh rate if enabled.
This setting is only expose in Nvidia Control Panel for G-Sync monitors supporting refresh rates above 60 Hz.

* **Triple buffering**

Toggles triple buffering in OpenGL games. Enabling this improves performance when vertical sync is also turned on.

* **Vertical Sync**

Controls vertical sync, or enables Fast Sync. Fast-Sync is essentially triple buffering for DirectX games, and is only applicable to frame rates above the refresh rate when regular V-Sync is disabled.

* **Vertical Sync Smooth AFR behavior** 

Toggles V-Sync smoothing behavior when V-Sync is enabled and SLI is active.

Official description:
```bash
Smooth Vsync is a new technology that can reduce stutter when Vsync is enabled and SLI is active.

When SLI is active and natural frame rates of games are below the refresh rate of your monitor, traditional vsync forces frame rates to quickly oscillate between the refresh rate and half the refresh rate (for example, between 60Hz and 30Hz). This variation is often perceived as stutter. Smooth Vsync improves this by locking into the sustainable frame rate of your game and only increasing the frame rate if the game performance moves sustainably above the refresh rate of your monitor. This does lower the average framerate of your game, but the experience in many cases is far better.
```

* **Vertical Sync Tea Control**

Toggles Adaptive V-Sync when vertical sync is enabled. Not available when G-Sync is enabled.

Official description:
```bash
Nothing is more distracting than frame rate stuttering and screen tearing. The first tends to occur when frame rates are low, the second when frame rates are high. Adaptive VSync is a smarter way to render frames using NVIDIA Control Panel software. At high framerates, VSync is enabled to eliminate tearing. At low frame rates, it's disabled to minimize stuttering.
```


## Antialiasing

* **Antialiasing - Behavior Flags**

These mostly exist as a method of governing usage of AA from Nvidia Control Panel, though they also affect Inspector as well. Make sure you are clearing out any flags in this field for a game profile when forcing AA as it will interfere and cause it not to work if you aren't careful.

* **Antialiasing - Gamma correction**

Gamma correction for MSAA.
- [x] Introduced with Half-Life 2 in 2004.
- [x]  Defaults to ON starting with Fermi GPUs.
- [x] Should not be set to OFF on modern hardware.

* **Antialiasing - Line gamma**

Applies gamma correction for singular lines (like wires) as compared to edges.

* **Antialiasing - Mode** 

Determines in what mode the anti-aliasing override of the display driver should function in for an application:
- [x] Application Controlled - The application itself controls anti-aliasing settings and techniques. The display driver does not override or enhance the anti-aliasing setting the application configures.
- [x] Override Application Setting - The display drivers overrides the anti-aliasing setting of the application. This allows one to force anti-aliasing from the display driver. General rule of thumb is to disable any in-game anti-aliasing/MSAA when using this to avoid conflict. There are exceptions though; generally noted in the Anti-Aliasing Compatibility Flags document.
- [x] Enhance Application Setting - Enhances the anti-aliasing of a game (e.g. enhance in-game MSAA with TrSSAA), which can provide higher quality and greater reliability for applications with built-in support for anti-aliasing. You must set any anti-aliasing level within the application for this mode to work with the Antialiasing - Setting override.
- [x] Use Override Application Setting if the application does not have built-in anti-aliasing settings or if the application does not support anti-aliasing when HDR rendering is enabled. When dealing with modern games, you will most likely want to use this option and not any of the other two.
- [x] Enhance Application Setting is entirely dependent on the implementation of MSAA in the application itself. This is can be hit or miss in modern DirectX 10+ games; more often than not either it does not work at all, breaks something, or looks very bad. See Enhance application setting for more information.

* **Antialiasing - Setting**

This is where the specific method of forced/enhanced MSAA is set.

* **Antialiasing - Transparency Multisampling**

The official explanation is given [here](http://http.download.nvidia.com/developer/SDK/Individual_Samples/DEMOS/Direct3D9/src/AntiAliasingWithTransparency/docs/AntiAliasingWithTransparency.pdf) 

* **Antialiasing - Transparency Supersampling**

Check the describtion over [here](http://www.tweakguides.com/NVFORCE_6.html).

* **Enable Maxwell sample interleaving (MFAA)**

This enables Nvidia's Multi Frame Anti Aliasing mode. This only works in DXGI (DX10+) and requires either the game to have MSAA enabled in the game or MSAA to be forced. What it does is change the sub sample grid pattern every frame and then is reconstructed in motion with a "Temporal Synthesis Filter" as Nvidia calls it.
There are some caveats to using this though.

* **NVIDIA Predefined FXAA Usage** 

Controls whether Nvidia's FXAA implementation is allowed to be enabled for an application through Nvidia Control Panel (primarily) or Nvidia Profile Inspector.

* **Toggle FXAA Indicator on or off** 

* **Toggle FXAA on or off**

FXAA is a fast shader-based post-processing technique that can be applied to any application, including those which do not support other forms of hardware-based antialiasing. FXAA can also be used in conjunction with other antialiasing settings to improve overall image quality.
- [x] Turn FXAA On to improve image quality with a lesser performance impact than other antialiasing settings.
- [x] Turn FXAA Off if you notice artifacts or dithering around the edges of objects, particularly around text.

Enabling this setting globally may affect all programs rendered on the GPU, including video players and the Windows desktop.


## Texture Filtering

* **Antistropic filtering mode**

Toggles the built-in anisotropic filtering override of the display drivers. 16x is the best and max quality you can choose.

It is possible to add a global override that forces anisotropic filtering on all games. This can solve texture filtering issues that would otherwise exist in games that have mediocre texture filtering. 

* **Antistropic filtering setting**

Controls the level of texture filtering the driver override applies, if Anisotropic filtering mode is set to User-defined / Off. 
  
* **Prevent Antistropic filtering**

Similar to AA Behavior Flags, if this is set to On it will ignore user-defined driver overrides. Some games default to this, such as Quake 4, RAGE, Doom (2016), Far Cry 3, and Far Cry 3: Blood Dragon.

* **Texture filtering - Antistrophic filter optimization**

Anisotropic filter optimization improves performance by limiting trilinear filtering to the primary texture stage where the general appearance and color of objects is determined. Bilinear filtering is used for all other stages, such as those used for lighting, shadows, and other effects. This setting only affects DirectX programs.
- [x] Select On for higher performance with a minimal loss in image quality
- [x] Select Offif you see shimmering on objects

* **Texture filtering - Antistrophic sample optimization**

Anisotropic sample optimization limits the number of anisotropic samples used based on texel size. This setting only affects DirectX programs.
- [x] Select On for higher performance with a minimal loss in image quality
- [x] Select Off if you see shimmering on objects

* **Texture filtering - Driver Controlled LOD Bias**

When using SGSSAA with this enabled will allow the driver to compute it's own negative LOD bias for textures to help improve sharpness (at cost of potential for more aliasing) for those who prefer it. It's generally less than the fixed amounts that are recommended. Manual LOD bias will be ignored when this is enabled.

* **Texture filtering - LOD Bias (DX)**

The level of detail bias setting for textures in DirectX applications. This normally only works under 2 circumstances, both of which requires Driver Controlled LoD Bias set to Off.

* **Texture filtering - LOD Bias (OGL)**

Identical to Texture Filtering - LOD Bias (DX) but applies to OpenGL applications instead.

* **Texture filtering - Negative LOD bias**

Some applications use negative LOD bias to sharpen texture filtering. This sharpens the stationary image but introduces aliasing ("shimmering") when the scene is in motion. This setting controls whether negative LOD bias are clamped (not allowed) or allowed. This togle has no effect on Fermi GPU's and beyond because clamps are by default on those GPUs. 

* **Texture filtering - Quality**

This setting allows you to decide if you would prefer performance, quality, or a balance between the two. If you change this using the Nvidia Control Panel, the control panel will make all of the appropriate texture filtering adjustments based on the selected preference.

* **Texture filtering - trilinear optimization**

Trilinear optimization improves texture filtering performance by allowing bilinear filtering on textures in parts of the scene where trilinear filtering is not necessary. This setting only affects DirectX applications.

Disabled if Texture Filtering - Quality is set to High Quality.


## Common

* **Ambient Occlusion setting**

This setting determines what mode of ambient occlusion is to be used when forced in games with no built-in support for it:
- [x] Performance
- [x] Quality
- [x] High Quality

* **Ambient Occlusion usage** 

Set this to Enabled when using forced ambient occlusion.

* **CUDA - Force P2 State** 

GeForce cards automatically switch (down) to P2 when they are used for compute. 
- [x] Level 2 = P2 State
- [x] Level 3 = P0 State (max)

* **Extension limit** 

Extension limit indicates whether the driver extension string has been trimmed for compatibility with particular applications. Some older applications cannot process long extension strings and will crash if extensions are unlimited.
- [x] If you are using an older OpenGL application, turning this option on may prevent crashing
- [x] If you are using a newer OpenGL application, you should turn this option off.

* Multi-display/mixed-GPU acceleration 

This controls GPU-based acceleration in OpenGL applications and will have no effect on performance on DirectX platforms. 

* **OpenGL - Version Override**

Some applications need the OGL identification string especially if they´re calling for OGL version 2.0. this flag allows to change this manually.

* **Power managment mode**

This allows you to set a preference for the performance level of the graphics cardwhen running 3D applications. It is recommended to configure this on a per-game basis using game-specific profiles, to prevent unnecessary power draw while not gaming.

- [x] Adaptive
Automatically determines whether to use a lower clock speed for games and apps.

Setting power management mode from Adaptive to Maximum Performance can improve performance in certain applications when the GPU is throttling the clock speeds incorrectly.

- [x] Optimal power
Same as Adaptive, but will not re-render frames when the GPU workload is idle; instead it will just display the previous frame.

The default power management mode on modern graphics cards.

- [x] Prefer maximum performance

Prevents the GPU from switching to a lower clock speed for games and apps.

* **Shadercache** 

Enables or disables the shader cache since nVidia 337.88, which saves compiled shaders to your hard drive to improve game performance. 

* **Show PhysX Visual Indicator**

Enables a on-screen status indicator of when PhysX is being used. If PhysX is not being used, the indicator is not shown at all.

* **Threaded optimization**

Allows applications to take advantage of multiple CPUs. Most newer applications should benefit from the Auto or On options. This setting should be turned off for most older applications.


## SLI

* **Antialiasing - SLI AA**

This determines whether a Nvidia SLI setup splits the MSAA workload between the available GPUs

* **Disable SLI (Explicity set through NVAPI)**

The documentation can be found [here](https://docs.nvidia.com/gameworks/content/gameworkslibrary/coresdk/nvapi/group__dx.html).

* **Number of GPUs to use on SLI rendering mode**

* NVIDIA predefined number of GPUs to use on SLI rendering mode**

* **NVIDIA predefined number of GPUs to use on SLI rendering mode on DX10**
  
* **NVIDIA predefined SLI mode**

* **NVIDIA predefined SLI mode on DirectX 10**

* **SLI indicator**

Enables a semi-transparent on-screen status indicator of when SLI is being used and how the workload is split between the cards.

* **SLI rendering mode**

There are [five SLI rendering modes](https://docs.nvidia.com/gameworks/content/technologies/desktop/sli.htm) available:
- [x] Alternate Frame Rendering (AFR)
- [x] Split Frame Rendering (SFR)
- [x] Boost Performance Hybrid SLI
- [x] SLIAA
- [x] Compatibility mode


## Stereo

These options are all releated to 3D Vision.

* **Force Stereo shuttering**

3D Vision stereo shuttering, the option is only relevnt if "Set up stereoscopic 3D window" was enabled. 

* **LaserXAdjust**

3D Vision Laser Sight X-axis adjustment. 

* **LaserYAdjust** 

3D Vision Laser Sight Y-axis adjustment. 

* **Stereo - Display mode**

This setting allows you to choose the appropriate display mode for shutter glasses, stereo displays, and other hardware. Refer to the hardware documentation to determine which mode to use.

* **Stereo - Dongle Support**

Enables 3D Vision dongle support, only relevant if you use 3D Vision and have a dongle for it. 

* **Stereo - Enable**

Enables stereo in OpenGL applications.

* **Stereo - Swap eyes**

Swaps left/right in NVIDIA Vision 2+. This option is relevant if you use a 3D TV) and want to use stereoscopic 3D.

* **Stereo - Swap mode**

See [here](https://nvidia.custhelp.com/app/answers/detail/a_id/3012/~/how-to-configure-passive-or-dual-pipe-stereo-with-quadro-cards-in-windows-7.) or [here](https://www.nvidia.com/object/page_pulled_off_gz_stereo.html) for a detailed explanation. 

* **StereoConvergence** 

Another 3D Vision option which [adjust the convergence](https://nvidia.custhelp.com/app/answers/detail/a_id/2943/~/how-do-i-adjust-convergence-in-my-game%3F).

* **StereoCutoff**

There is no official describtion given, see here for _some_ [details](https://forums.geforce.com/default/topic/926916/3d-vision/nvidia-inspector-gt-gt-gt-new-2-1-3-10-/post/4925834/#4925834).

* **StereoCutoffDepthFar**

* **StereoCutoffDepthNear**

* **StereoFlagsDX10**

* **StereoMemoEnabled**

* **StereoProfile**

* **StereoTextureEnable**

* **StereoUseMatrix**


## Other

* **Ansel flags for enabled applications**

* **Application Profile Notification Popup Timeout**

* **Battery Boost**

* **Battery Boost Application FPS**

* **Buffer-flipping mode**

Determines how the video buffer is copied to the screen. This setting only affects OpenGL programs.
- [x] Auto-select allows the driver to determine the best method based on the hardware configuratoin.
- [x] Use block transfer produces smoother drawings for some applications, though it may be slower at higher frame rates and introduce tearing.

* **Deep color for 3D applications**

* **Display the VRR Overlay Indicator**

* **Do not display this profile in the Control Panel**

Hides the profile from being listed in Nvidia Control Panel > Manage 3D Settings > Program Settings.

* **Enable Ansel**

Toggles [Ansel](https://www.geforce.com/hardware/technology/ansel) (NvCamera) for the application. This is enabled by default and results in the display drivers injecting the DLL files for Ansel in all applications.

* **Enable application for Optimus**

On an Optimus laptop, controls whether the selected application runs on the dedicated Nvidia GPU or the integrated GPU.

* **Enable GTX950 special features**

* **Enable NV_gpu_multicast extension**

* **Enable overlay**

Allows the use of OpenGL overlay planes in programs. Typically used if a program fails to render OpenGL planes.

* **Event Log Severity Threshold**

* **Export Performance Counters**

* **Export Performance Counters for DX9 only**

* **Exported Overlay pixel types**

Determines whether the driver supports RGB or color indexed OpenGL overlay plane formats. Typically used if a program fails to set the proper OpenGL overlay plane format.

* **Frame Rate Monitor**

* **Frame Rate Monitor Control**

* **G-SYNC Compatibility**

* **High level control of the rendering quality on OpenGL**

* **ICafe Settings**

* **List of Universal GPU ids**

* Maximum AA samples allowed for a given application** 

* **Maximum frames allowed**

* **Maximum GPU Power**

* **Maximum resolution allowed for a given application**

* **Memory Allocation Policy**

This defines how workstation feature resource allocation is performed.
- [x] As Needed (default) - Resources for workstation features are allocated as needed resulting in the minimum amount of resource consumption. Feature activation or deactivation often causes mode-sets.
- [x] Moderate pre-allocation - Resources for the first workstation feature activated are statically allocated at system boot and persist thereafter. This will use more GPU and system memory, but will prevent mode-sets when activating or deactivating a single feature. Invocation of additional workstation features will still cause mode-sets.
- [x] Aggressive pre-allocation - Resources for all workstation features are statically allocated at system boot and persist thereafter. This will use the most GPU and system memory, but will prevent mode-sets when activating or deactivating all workstation features.

* **NVIDIA Predefined Ansel Usage**

* **NVIDIA Quality upscaling**

* **OpenGL default swap interval**

* **OpenGL default swap interval fraction**

* **OpenGL default swap sign**

* **Optimus flags for enabled applications**

* **PowerThrottle**

* **Preferred OpenGL GPU**

* **Set CFR mode**

* **Shim Rendering Mode Options per applications for Optimus** 

* **SILK Smoothness**

Silk reduces stutters in games caused by variable CPU or GPU workloads by smoothing out animation and presentation cadence using animation prediction and post render smoothing buffer.
- [x] Off – Silk is disabled.
- [x] Low – Moderate smoothing is enabled and most microstutter is eliminated.
- [x] Medium – Many stutters and hitches are removed in typical games.
- [x] High – More smoothing is applied and may result in observable input lag.
- [x] Ultra – Maximum smoothing is applied and most stutters and hitches in games are eliminated. Lag may be unacceptable in some games.

Selecting High or Ultra settings for silk can increase noticeable lag when playing, and may not be appropriate for first person shooters or competitive gaming. It's recommend to leave it untouched or set it to medium. 

* **Steam Application ID**

* **Unified back / depth buffer**

* **VAB Default Data**

* **Variable refresh Rate**

* **Virtual Reality pre-rendered frames**

Limits the number of frames the CPU can prepare before the frames are processed by the GPU. Lower latency is preferable for virtual reality head sets.

* Vsync - Behavior Flags

* **Whisper Mode**

* **Whisper Mode Application FPS**

  
## Unknown

These are unknown settings or overrides that Nvidia Profile Inspector is not aware of what they determine or controls.

* **0x00666634**

* **0x00666665**

* **0x00675665**

* **0x00676635**

* **0x10C158AD (Optimize for Compute Performance)**

- [x] 0 - disabled
- [x] 1 - enabled

* **0x11FBDF11**

* **0x80303A19 (269 Profiles)**

* **0x80857A28 (878 Profiles)**

* **0x809D5F60 (389 Profiles)**


## References

* [Blur Busters - G-SYNC 101: In-game vs. External FPS Limiters](https://www.blurbusters.com/gsync/gsync101-input-lag-tests-and-settings/11/)
* [Nvidia Profile Inspector](https://pcgamingwiki.com/wiki/NVIDIA_Profile_Inspector)
* [DisplayLag - Reduce Input Lag in PC Games: The Definitive Guide](https://displaylag.com/reduce-input-lag-in-pc-games-the-definitive-guide/) 
* [What is Smooth Vsync?](https://nvidia.custhelp.com/app/answers/detail/a_id/3283/~/what-is-smooth-vsync)
* [Adaptive V-Sync](https://www.geforce.com/hardware/technology/adaptive-vsync)
* [Introducing SLI Antialiasing: The Ultimate in Visual Quality](https://www.nvidia.com/object/slizone_sliAA_howto1.html)
* [Introduction to SLI](https://docs.nvidia.com/gameworks/content/technologies/desktop/sli.htm)
* [How to use Ansel](https://www.geforce.com/whats-new/guides/how-to-use-ansel)
* [Complete Nvidia Ansel guide: All the games and graphics cards that support it](https://www.finder.com.au/nvidia-ansel)
* [NVIDIA SLI Alternate Frame Rendering](https://docs.unrealengine.com/en-us/Engine/Rendering/Nvidia/NVIDIAAlternateFrameRendering)
* [Nvidia Inspector introduction and Guide](https://forums.guru3d.com/threads/nvidia-inspector-introduction-and-guide.403676/)
* [3D Surround Technology](https://www.nvidia.com/object/3d-vision-surround-technology.html)
* [Driver Profile Settings](http://wiki.bo3b.net/index.php?title=Driver_Profile_Settings)

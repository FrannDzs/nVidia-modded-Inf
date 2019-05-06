## Info

It's possible to enable/disable [software based telemetry](https://en.wikipedia.org/wiki/Telemetry#Software) via .inf file. The defaults are set to 1, which means it's enabled (opt-out by default).


## Global toggle

* `NvSupportTelemetry = 1` (Default)
* `NvSupportTelemetry = 0` (Disabled)


## Disable software component (plugin) based telemetry

* `NvTelemetry64.dll = 1` (Default)
* `NvTelemetry64.dll = 0` (Disabled)


Contained in the driver package:
* `NvInstallerUtil.dll` (NVI2 folder)
* `NVNetworkService.exe` (NVI2 folder)
* `NVNetworkServiceAPI.dll` (NVI2 folder)


## Firewall

At this point it's unclear if blocking the software telemetry with the Windows own firewall is 100% _effective_ since the submitted data are tunneled & encrypted [_needs final confirmation_].

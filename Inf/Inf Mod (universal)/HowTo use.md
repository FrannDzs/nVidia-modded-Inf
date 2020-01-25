### Instructions

* Download the official nVidia drivers.
* Extract the driver package via WinRar or 7-Zip.
* Use the corresponding .inf file for Standard or DCH driver and rename the downloaded .inf file to `nv_dispi.inf`.
* Override it with the existent one or rename it to `nv_dispi.inf.bak` so that you have a backup.
* Copy the line 9 e.g. `DriverVer   = 01/01/2020, 27.27.27.9999` from your original .inf and replace the line with the modded one.
* Install the driver - make sure you disable [Driver Signature Verification](https://www.howtogeek.com/167723/how-to-disable-driver-signature-verification-on-64-bit-windows-8.1-so-that-you-can-install-unsigned-drivers/) in case you can't install the modded driver.
* Done.
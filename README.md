# Arduino Core for nRF51 micro boards

[![Build Status](https://github.com/sandeepmistry/arduino-nRF5/actions/workflows/compile.yml/badge.svg)](https://github.com/sandeepmistry/arduino-nRF5/actions/workflows/compile.yml) 

Program your nRF51 micro board using the [Arduino](https://www.arduino.cc) IDE.
Does not require a custom bootloader on the device.
## Installing

### Board Manager

 1. [Download and install the Arduino IDE](https://www.arduino.cc/en/Main/Software) 
 2. Start the Arduino IDE
 3. Go into Preferences
 4. Add ```https://sandeepmistry.github.io/arduino-nRF5/package_nRF5_boards_index.json``` as an "Additional Board Manager URL"
 5. Open the Boards Manager from the Tools -> Board menu and install "Nordic Semiconductor nRF5 Boards"
 6. Select your nRF5 board from the Tools -> Board menu

__NOTE:__ During installation it takes the Arduino IDE a few minutes to extract the tools after they have been downloaded, please be patient.

#### OS Specific Setup

##### OS X

No additional setup required.

##### Linux

For 64-bit Linux users,  ```libc6:i386```, ```libstdc++6:i386```, ```libncurses5:i386``` and ```libudev1:i386``` need to be installed :
  * ```sudo dpkg --add-architecture i386```
  * ```sudo apt-get update```
  * ```sudo apt-get -y install libc6:i386 libstdc++6:i386 libncurses5:i386 libudev1:i386```

#####  Windows

###### Driver Setup for mbed devices
 Download [mbed Windows Serial driver](https://developer.mbed.org/handbook/Windows-serial-configuration#1-download-the-mbed-windows-serial-port)

###### Driver Setup for Segger J-Link

 1. Download [Zadig](http://zadig.akeo.ie)
 2. Plugin Segger J-Link or DK board
 3. Start ```Zadig```
 4. Select ```Options -> List All Devices```
 5. Plug and unplug your device to find what changes, and select the ```Interface 2``` from the device dropdown
 6. Click ```Replace Driver```

__NOTE__: To roll back to the original driver go to: Device Manager -> Right click on device -> Check box for "Delete the driver software for this device" and click Uninstall

## BLE

This Arduino Core does **not** contain any Arduino style API's for BLE functionality. All the relevant Nordic SoftDevice (S110, S130, S132) header files are included build path when a SoftDevice is selected via the `Tools` menu.

### Recommend BLE Libraries

 * [BLEPeripheral](https://github.com/sandeepmistry/arduino-BLEPeripheral)
   * v0.3.0 and greater, available via the Arduino IDE's library manager.
   * Supports peripheral mode only.

## Credits

This core is based on the [Arduino Core for Nordic Semiconductor nRF5 based boards](https://github.com/sandeepmistry/arduino-nRF5) and licensed under the same [LGPL License](LICENSE)

The following tools are used:

 * [GCC ARM Embedded](https://launchpad.net/gcc-arm-embedded) as the compiler
 * A [forked](https://github.com/sandeepmistry/openocd-code-nrf5) version of [OpenOCD](http://openocd.org) to flash sketches

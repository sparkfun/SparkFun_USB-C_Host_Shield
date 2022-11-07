SparkFun USB-C Host Shield
========================================

<p align="center">
  <a href="https://github.com/sparkfun/SparkFun_USB-C_Host_Shield/issues" alt="Issues">
    <img src="https://img.shields.io/github/issues/sparkfun/SparkFun_USB-C_Host_Shield.svg" /></a>
  <a href="https://github.com/sparkfun/SparkFun_USB-C_Host_Shield/actions" alt="Actions">
    <img src="https://github.com/sparkfun/SparkFun_USB-C_Host_Shield/actions/workflows/mkdocs.yml/badge.svg" /></a>
  <a href="https://github.com/sparkfun/SparkFun_USB-C_Host_Shield/blob/master/LICENSE.md" alt="License">
    <img src="https://img.shields.io/badge/license-CC%20BY--SA%204.0-EF9421.svg" /></a>
  <a href="https://twitter.com/intent/follow?screen_name=sparkfun">
    <img src="https://img.shields.io/twitter/follow/sparkfun.svg?style=social&logo=twitter" alt="follow on Twitter"></a>
</p>


[![SparkFun USB-C Host Shield](https://cdn.sparkfun.com/assets/parts/1/9/9/6/8/21247Diagonal.jpg)](https://www.sparkfun.com/products/21247)

*[SparkFun USB-C Host Shield (DEV-21247)](https://www.sparkfun.com/products/21247)*

This new version updates the USB Type-A connector to a USB-C connector and provides users with the option to power the shield from the `5V` or  `VIN` pins. The USB-C female connector also supplies 5V as any normal USB *(downward facing)* port would.

The SparkFun USB Host Shield contains all of the digital logic and analog circuitry necessary to implement a USB peripheral/host controller with your Arduino. This means you could use your Arduino to interface with and control any USB 2.0 compatible device - thumbdrives, digital cameras, bluetooth dongles, and much more!

A four-wire serial interface is used to communicate with the host controller chip, so the shield connects the Arduino's hardware SPI pins (D10-13) to the MAX3421E. All SPI signals are sent through a hex converter to step them down to 3.3V.


Repository Contents
-------------------

* **[/docs](/docs/)** - Online documentation files
    * [board_files](/docs/board_files/) - Files for the product design
        * [Eagle design files](/docs/board_files/eagle_files.zip) (.zip)
        * [Schematic](/docs/board_files/schematic.pdf) (.pdf)
        * [Dimensions](/docs/board_files/dimensions.pdf) (.pdf)
    * [component_documentation](/docs/component_documentation/) - Datasheets and manuals for hardware components
    * [img/hookup_guide/](/docs/img/hookup_guide/) - Images for hookup guide documentation
* **[/Firmware](/Firmware/)** - Example sketches demonstrating extra peripherals
* **[/Hardware](/Hardware/)** - Eagle design files (.brd, .sch)

Documentation
--------------
* **[Hookup Guide (mkdocs)](http://docs.sparkfun.com/SparkFun_USB-C_Host_Shield/)** - Hookup guide for the USB-C Host Shield hosted by GitHub pages.

Product Versions
----------------
* USB-C Host Shield (USB-C variant)
  * [DEV-21247](https://www.sparkfun.com/products/21247)- v1.0, Initial Release
* USB Host Shield
  * [DEV-09947](https://www.sparkfun.com/products/retired/9947)- v2.0, Fixes `GPX` and `RESET` pin connections
  * [DEV-09628](https://www.sparkfun.com/products/retired/9628)- v1.0, Initial Release

License Information
-------------------

This product is _**open source**_! 

Please review the LICENSE.md file for license information. 

If you have any questions or concerns on licensing, please contact technical support on our [SparkFun forums](https://forum.sparkfun.com/viewforum.php?f=152).

Distributed as-is; no warranty is given.

- Your friends at SparkFun.

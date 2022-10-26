!!! note
    This guide is specific to the [USB-C Host Shield](https://www.sparkfun.com/products/21247) board variant. For the variants with the USB (Type-A) connector, please refer to [this guide by Hardware Fun](https://hardwarefun.com/tutorials/using-usb-host-shield-with-arduino).

<p align="center">
  <a href="https://github.com/sparkfun/SparkFun_USB-C_Host_Shield/issues" alt="Issues">
    <img src="https://img.shields.io/github/issues/sparkfun/SparkFun_USB-C_Host_Shield.svg" /></a>
  <a href="https://github.com/sparkfun/SparkFun_USB-C_Host_Shield/blob/master/LICENSE.md" alt="License">
    <img src="https://img.shields.io/badge/license-CC%20BY--SA%204.0-EF9421.svg" /></a>
  <a href="https://twitter.com/intent/follow?screen_name=sparkfun">
    <img src="https://img.shields.io/twitter/follow/sparkfun.svg?style=social&logo=twitter" alt="follow on Twitter"></a>
</p>

# SparkFun USB-C Host Shield
The [SparkFun USB-C Host Shield](https://www.sparkfun.com/products/21247) has similar features to our previous [USB Host Shield (v2)](https://www.sparkfun.com/products/retired/9947), but we upgraded the Type-A connector to a USB-C connector. Additionally, the board provides users with the option to select either the `5V` or  `VIN` pin to power the shield and in turn, supply the **5V** to the USB port.

<center>
[![SparkFun USB-C Host Shield](https://cdn.sparkfun.com/r/500-500/assets/parts/1/9/9/6/8/21247Diagonal.jpg)](https://www.sparkfun.com/products/21247)
<br>
### [SparkFun USB-C Host Shield](https://www.sparkfun.com/products/21247)
(DEV-21247)
</center>

<center>
<iframe width="458" height="257" src="https://www.youtube.com/embed/g2MgO2fjqsw" title="Product Showcase: SparkFun USB-C Host Shield" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

The SparkFun USB Host Shield contains all of the digital logic and analog circuitry necessary to implement a USB peripheral/host controller with your Arduino board. This means you could use your Arduino microcontroller to interface with and control any USB 2.0 compatible device - flashdrives, digital cameras, Bluetooth dongles, and much more!

A four-wire serial interface is used to communicate with the host controller chip, so the shield connects the Arduino's hardware SPI pins (D10-13) to the MAX3421E. All SPI signals are sent through a hex converter to keep the shield compatible with 5V Arduino boards.
## Arduino IDE
!!! note
	For first-time users, who have never programmed before and are looking to use the Arduino IDE, we recommend beginning with the <a href="https://www.sparkfun.com/products/15631">SparkFun Inventor's Kit (SIK)</a>, which includes a simple board like the <a href="https://www.sparkfun.com/products/11224">Arduino Uno</a> or <a href="https://www.sparkfun.com/products/15123">SparkFun RedBoard</a> and is designed to help users get started programming with the Arduino IDE.

Most users may already be familiar with the Arduino IDE and its use. However, for those of you who have never heard the name *Arduino* before, feel free to check out the [Arduino website](https://www.arduino.cc/en/Guide/HomePage). To get started with using the Arduino IDE, check out our tutorials below:


<table class="pdf" style="border-style:none" align="center">
	<tr>
		<td align="center">
			<a class="thumb" href="https://learn.sparkfun.com/tutorials/50">
				<img src="https://cdn.sparkfun.com/c/264-148/assets/3/b/6/e/b/512e66bece395f492b000000.jpg" alt="What is an Arduino?">
				<h3 class="title">What is an Arduino?</h3>
			</a>
		</td>
		<td align="center">
			<a class="thumb" href="https://learn.sparkfun.com/tutorials/61">
				<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/1/arduinoThumb.jpg" alt="Installing Arduino IDE">
				<h3 class="title">Installing Arduino IDE</h3>
			</a>
		</td>
		<td align="center">
			<a class="thumb" href="https://learn.sparkfun.com/tutorials/15">
				<img src="https://cdn.sparkfun.com/c/264-148/assets/b/e/4/b/2/50f04b99ce395fd95e000001.jpg" alt="Installing an Arduino Library">
				<h3 class="title">Installing an Arduino Library</h3>
			</a>
		</td>
		<td align="center">
			<a class="thumb" href="https://learn.sparkfun.com/tutorials/1265">
				<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/1/2/6/5/sparkfun_boards.PNG" alt="Installing Board Definitions in the Arduino IDE">
				<h3 class="title">Installing Board Definitions in the Arduino IDE</h3>
			</a>
		</td>
	</tr>
</table>


<div class="grid cards" markdown align="center">

-   <a href="https://learn.sparkfun.com/tutorials/50">**What is an Arduino?**

	---

	<figure markdown>
	![What is an Arduino?](https://cdn.sparkfun.com/c/264-148/assets/3/b/6/e/b/512e66bece395f492b000000.jpg)
	</figure></a>

-   <a href="https://learn.sparkfun.com/tutorials/61">**Installing the Arduino IDE**

	---
	
	<figure markdown>
	![Installing the Arduino IDE](https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/1/arduinoThumb.jpg)
	</figure></a>

-   <a href="https://learn.sparkfun.com/tutorials/15">**Installing an Arduino Library**

	---
	
	<figure markdown>
	![Installing an Arduino Library](https://cdn.sparkfun.com/c/264-148/assets/b/e/4/b/2/50f04b99ce395fd95e000001.jpg)
	</figure></a>

-   <a href="https://learn.sparkfun.com/tutorials/1265">**Installing Board Definitions in the Arduino IDE**

	---
	
	<figure markdown>
	![Installing Board Definitions in the Arduino IDE](https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/1/2/6/5/sparkfun_boards.PNG)
	</figure></a>
</div>


### USB Host Library
The [USB Host Library Rev. 2.0](https://github.com/felis/USB_Host_Shield_2.0) can be installed from the library manager in the Arduino IDE.

<center>
[![USB Host Library](./img/hookup_guide/arduino_library.jpg){ width="400" }](./img/hookup_guide/arduino_library.jpg)<br>
*USB Host Library in the library manager of the Arduino IDE. (Click to enlarge)*
</center>

*For more details about the library, check out the [online documentation](https://felis.github.io/USB_Host_Shield_2.0/).*


#### Supported Boards
For a detailed and up-to-date list of boards supported by this library, check out the [`README.md` of the GitHub repository](https://github.com/felis/USB_Host_Shield_2.0#boards):

* All official Arduino AVR boards (Uno, Duemilanove, Mega, Mega 2560, Mega ADK, Leonardo etc.)
* Arduino Due
* Teensy (Teensy++ 1.0, Teensy 2.0, Teensy++ 2.0, Teensy 3.x, Teensy LC and Teensy 4.x)
	* For the Teensy 3.x, download this SPI library as well: <https://github.com/xxxajk/spi4teensy3> and add ```#include <spi4teensy3.h>``` to the `*.ino` sketch file.
* STM32F4
	* Take a look at the following example code: <https://github.com/Lauszus/Nucleo_F446RE_USBHost>.
* ESP8266 is supported using the [ESP8266 Arduino core](https://github.com/esp8266/Arduino)
	* Uses pins `15` and `5` for `CS` and `INT`, respectively.
	  * `GPIO16` is **NOT** usable.
	  * `GPIO6` to `11` are also **NOT** usable.
* ESP32 is supported using the [arduino-esp32](https://github.com/espressif/arduino-esp32/)
	* GPIO5 : `CS`, GPIO17 : `INT`, GPIO18 : `SCK`, GPIO19 : `POCI`, GPIO23 : `PICO`


#### I/O Pin Modifications
The SPI pins used by this library are dictated by [SPI library](https://www.arduino.cc/reference/en/language/functions/communication/spi/) for the Arduino core being utilized and cannot be changed easily. It is recommended that the default pins of the SPI library be utilized.

The library also utilizes a `CS` and `INT` pin. These pins can be reconfigured in the library by modifying the [UsbCore.h](https://github.com/felis/USB_Host_Shield_2.0/blob/master/UsbCore.h#L36-L58) file:

```C++
typedef MAX3421e< "CS Pin", "INT Pin" > MAX3421E;
```

For instance, to reconfigure the `CS` pin to `D7` and the `INT` pin to `D2` of the Arduino Uno, [line 58](https://github.com/felis/USB_Host_Shield_2.0/blob/master/UsbCore.h#L58) should read:

```C++
typedef MAX3421e<P7, P2> MAX3421E;
```



## RedBoard Plus
!!! note
	The following instructions are specific to the RedBoard Plus. 

<center>
[![RedBoard Plus Hookup Guide](https://cdn.sparkfun.com/c/500-282/assets/learn_tutorials/1/7/5/8/18158-SparkFun_RedBoard_Plus-01.jpg)](https://learn.sparkfun.com/tutorials/1758)<br>
[**RedBoard Plus Hookup Guide**](https://learn.sparkfun.com/tutorials/1758)
</center>


### CH340 Driver
Users will need to install the appropriate driver for their computer to recognize the serial-to-UART chip on their board/adapter. Most of the latest operating systems will recognize the CH340C chip on the board and automatically install the required driver.

*To manually install the CH340 driver on their computer, users can download it from the [WCH website](http://www.wch-ic.com/products/CH340.html?). For more information, check out our [How to Install CH340 Drivers Tutorial](https://www.sparkfun.com/ch340).*

<center>
[![How to Install CH340 Drivers](https://cdn.sparkfun.com/c/500-282/assets/learn_tutorials/9/0/8/USB-to-serial_converter_CH340-closeup.jpg)](https://learn.sparkfun.com/tutorials/908)<br>
[**How to Install CH340 Drivers**](https://learn.sparkfun.com/tutorials/908)
</center>


### Arduino IDE
When selecting a board to program in the Arduino IDE, users should select the **Arduino Uno** from the Tools drop-down menu _(_i.e. **Tools** > **Board** > **Arduino AVR Boards** > **Arduino Uno**)_.

<center>
[![Board Selection](./img/hookup_guide/board_selection.png){ width="400" }](./img/hookup_guide/board_selection.png)<br>
_Select the **Arduino Uno** from the Tools drop-down menu in the Arduino IDE. (Click to enlarge)_
</center>
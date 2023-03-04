<!-- # Introduction -->

!!! attention
	This guide is specific to the [USB-C Host Shield](https://www.sparkfun.com/products/21247) board variant. For the variants with the USB (Type-A) connector, please refer to [this guide by Hardware Fun](https://hardwarefun.com/tutorials/using-usb-host-shield-with-arduino).


<div class="grid cards desc" markdown>

<!-- **SparkFun USB-C Host Shield** (DEV-21247)  -->
-   **SKU:** DEV-21247
	
	---
	
	<figure markdown>
	[![SparkFun USB-C Host Shield](https://cdn.sparkfun.com/assets/parts/2/1/0/0/8/SparkFun_USB-C_Host_Shield-_01.jpg "Click to enlarge")](https://cdn.sparkfun.com/assets/parts/2/1/0/0/8/SparkFun_USB-C_Host_Shield-_01.jpg)
	</figure>


-	The [SparkFun USB-C Host Shield](https://www.sparkfun.com/products/21247) has similar features to our previous [USB Host Shield (v2)](https://www.sparkfun.com/products/retired/9947), but we upgraded the USB Type-A connector to a USB-C connector. Additionally, the board provides users with the option to select either the `5V` or  `VIN` pin to power the shield and USB port.

	The SparkFun USB Host Shield contains all of the digital logic and analog circuitry necessary to implement a USB peripheral/host controller with your Arduino board. This means you could use your Arduino microcontroller to interface with and control any USB 2.0 compatible device - flash drives, digital cameras, Bluetooth dongles, and much more!

	A four-wire serial interface is used to communicate with the host controller chip, so the shield connects the Arduino's hardware SPI pins (D10-13) to the MAX3421E. While the logic-level for the shield is 3.3V, all the SPI signals are sent through a hex converter to keep the shield compatible with any 5V Arduino boards.

	<center>
	[Purchase from SparkFun :fontawesome-solid-cart-plus:](https://www.sparkfun.com/products/21247){ .md-button .md-button--primary }
	</center>

</div>

<table class="pdf" style="border-style:none;" markdown="1">
<tbody markdown="1">
<tr markdown="1">
<td align="center" width="35%" markdown="block">
[![SparkFun USB-C Host Shield](https://cdn.sparkfun.com/r/500-500/assets/parts/2/1/0/0/8/SparkFun_USB-C_Host_Shield-_01.jpg){ width=90% }](https://www.sparkfun.com/products/21247)
</td>
<td markdown="block">

The [SparkFun USB-C Host Shield](https://www.sparkfun.com/products/21247) has similar features to our previous [USB Host Shield (v2)](https://www.sparkfun.com/products/retired/9947), but we upgraded the USB Type-A connector to a USB-C connector. Additionally, the board provides users with the option to select either the `5V` or  `VIN` pin to power the shield and USB port.

The SparkFun USB Host Shield contains all of the digital logic and analog circuitry necessary to implement a USB peripheral/host controller with your Arduino board. This means you could use your Arduino microcontroller to interface with and control any USB 2.0 compatible device - flash drives, digital cameras, Bluetooth dongles, and much more!

A four-wire serial interface is used to communicate with the host controller chip, so the shield connects the Arduino's hardware SPI pins (D10-13) to the MAX3421E. While the logic-level for the shield is 3.3V, all the SPI signals are sent through a hex converter to keep the shield compatible with any 5V Arduino boards.

<center>
[Purchase from SparkFun :fontawesome-solid-cart-plus:](https://www.sparkfun.com/products/21247){ .md-button .md-button--primary }
</center>
</td>
</tr>
</tbody>
</table>


## Required Materials
To get started with the USB-C Host Shield, users will need a few additional items. Users may already have some of these items, feel free to modify your cart accordingly. For users just getting started with electronics, we have linked a few tutorials to establish a foundation of knowledge to follow along with this hookup guide.

* Computer with an operating system (OS) that is compatible with all the software installation requirements.
* A compatible microcontroller/Arduino board; we recommend the [SparkFun RedBoard Plus](https://www.sparkfun.com/products/18158).

	!!! warning
		The recommended Arduino library for the USB Host Shield is not compatible with all microcontrollers or boards. For a complete list of compatible microcontrollers and boards, please refer to the [`README.md` file](https://github.com/felis/USB_Host_Shield_2.0#boards) of USB Host Library Rev. 2.0.

* [USB 3.1 Cable A to C - 3 Foot](https://www.sparkfun.com/products/14743) - Used to interface with the RedBoard Plus (1)
{ .annotate }

	1.	If your computer doesn't have a USB-A slot or your microcontroller/Arduino board has a different USB connector, then choose an appropriate cable or adapter.

* [SparkFun USB-C Host Shield](https://www.sparkfun.com/products/21247)
* USB Peripheral Device *(i.e. [flash drive](https://www.sparkfun.com/products/14658), [game controller](https://www.sparkfun.com/products/17264), smartphone, etc.)* (1)
{ .annotate }

	1.	An [adapter](https://www.sparkfun.com/products/21870) or [cable](https://www.sparkfun.com/products/21271) may be necessary to interface with the peripheral device.

* Headers - Used to connect the shield to the Arduino board (1)
{ .annotate }

	1.	Check out some of the options for the [Arduino R3](https://www.sparkfun.com/products/11417)/Uno form factor boards below; otherwise, click here for a full selection of our available [headers](https://www.sparkfun.com/categories/381).


* Soldering Tools (1)
{ .annotate }

	1.	Check out the beginner tool kit below; otherwise, click here for a full selection of our available [soldering tools](https://www.sparkfun.com/categories/49).


<table class="pdf" style="border-style:none">
	<tr>
		<td>
			<a href="https://www.sparkfun.com/products/14743">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/1/2/9/7/2/14743-USB_3.1_Cable_A_to_C_-_3_Foot-01.jpg" alt="USB 3.1 Cable A to C - 3 Foot"></center>
				<h3 class="title">USB 3.1 Cable A to C - 3 Foot</h3>
			</a>
			CAB-14743
		</td>
		<td>
			<a href="https://www.sparkfun.com/products/18158">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/1/7/4/8/7/18158-SparkFun_RedBoard_Plus-01.jpg" alt="SparkFun RedBoard Plus">
				</center>
				<h3 class="title">SparkFun RedBoard Plus</h3>
			</a>
			DEV-18158
		</td>
		<td>
			<a href="https://www.sparkfun.com/products/21247">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/2/1/0/0/8/SparkFun_USB-C_Host_Shield-_01.jpg" alt="SparkFun USB-C Host Shield">
				</center>
				<h3 class="title">SparkFun USB-C Host Shield</h3>
			</a>
			DEV-21247
		</td>
	</tr>
	<tr>
		<td>
			<a href="https://www.sparkfun.com/products/116">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/1/0/6/00116-02-L.jpg" alt="Break Away Headers - Straight"></center>
				<h3 class="title">Break Away Headers - Straight</h3>
			</a>
			PRT-00116
		</td>
		<td>
			<a href="https://www.sparkfun.com/products/11417">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/7/2/1/6/11417-01a.jpg" alt="Arduino Stackable Header Kit - R3">
				</center>
				<h3 class="title">Arduino Stackable Header Kit - R3</h3>
			</a>
			PRT-11417
		</td>
	</tr>
	<tr>
		<td>
			<a href="https://www.sparkfun.com/products/14681">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/1/2/8/8/3/14681-SparkFun_Beginner_Tool_Kit.jpg" alt="SparkFun Beginner Tool Kit">
				</center>
				<h3 class="title">SparkFun Beginner Tool Kit</h3>
			</a>
			TOL-14681
		</td>
	</tr>
</table>


<div class="grid cards" markdown>

-   <a href="https://www.sparkfun.com/products/14743">**USB 3.1 Cable A to C - 3 Foot**<br>
	CAB-14743

	---

	<figure markdown>
	![USB 3.1 Cable A to C - 3 Foot](https://cdn.sparkfun.com/assets/parts/1/2/9/7/2/14743-USB_3.1_Cable_A_to_C_-_3_Foot-01.jpg)
	</figure></a>

-   <a href="https://www.sparkfun.com/products/18158">**SparkFun RedBoard Plus**<br>
	DEV-18158

	---
	
	<figure markdown>
	![SparkFun RedBoard Plus](https://cdn.sparkfun.com/assets/parts/1/7/4/8/7/18158-SparkFun_RedBoard_Plus-01.jpg)
	</figure></a>

-   <a href="https://www.sparkfun.com/products/21247">**SparkFun USB-C Host Shield**<br>
	DEV-21247

	---

	<figure markdown>
	![SparkFun USB-C Host Shield](https://cdn.sparkfun.com/assets/parts/2/1/0/0/8/SparkFun_USB-C_Host_Shield-_01.jpg)
	</figure></a>

-   <a href="https://www.sparkfun.com/products/116">**Break Away Headers - Straight**<br>
	PRT-00116

	---

	<figure markdown>
	![Break Away Headers - Straight](https://cdn.sparkfun.com/assets/parts/1/0/6/00116-02-L.jpg)
	</figure>
	</a>

-   <a href="https://www.sparkfun.com/products/11417">**Arduino Stackable Header Kit - R3**<br>
	PRT-11417

	---

	<figure markdown>
	![Arduino Stackable Header Kit - R3](https://cdn.sparkfun.com/assets/parts/7/2/1/6/11417-01a.jpg)
	</figure>
	</a>

-   <a href="https://www.sparkfun.com/products/14681">**SparkFun Beginner Tool Kit**<br>
	TOL-14681

	---

	<figure markdown>
	![SparkFun Beginner Tool Kit](https://cdn.sparkfun.com/assets/parts/1/2/8/8/3/14681-SparkFun_Beginner_Tool_Kit.jpg)
	</figure>
	</a>

</div>



!!! tip
	New to soldering? Check out our [Through-Hole Soldering Tutorial](https://learn.sparkfun.com/tutorials/5) for a quick introduction!
	<p align="center">
		<a href="https://learn.sparkfun.com/tutorials/5">How to Solder: Through-Hole Soldering<br>
		<img src="https://cdn.sparkfun.com/c/264-148/assets/e/3/9/9/4/51d9fbe1ce395f7a2a000000.jpg"></a>
	</p>



### Arduino Examples
The following products are used in the Arduino examples shown in this hookup guide. Users are welcome to choose other products; however, these have been tested and verified to work with the examples.


<table class="pdf" style="border-style:none">
	<tr>
		<td>
			<a href="https://www.sparkfun.com/products/21870">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/2/1/7/0/0/21870-_PRT-_01.jpg" alt="USB A (Female) to Type C (Male) Converter"></center>
				<h3 class="title">USB A (Female) to Type C (Male) Converter</h3>
			</a>
			COM-21870
		</td>
		<td>
			<a href="https://www.sparkfun.com/products/16905">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/1/5/8/3/4/16905-USB_-_C_to_C_cable-01.jpg" alt="USB 2.0 Type-C Cable - 1 Meter"></center>
				<h3 class="title">USB 2.0 Type-C Cable - 1 Meter</h3>
			</a>
			CAB-16905
		</td>
		<td>
			<a href="https://www.sparkfun.com/products/14658">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/1/2/8/5/0/14658-SparkFun_USB_Thumb_Drive__16GB_-01.jpg" alt="SparkFun USB Thumb Drive (16GB)"></center>
				<h3 class="title">SparkFun USB Thumb Drive (16GB)</h3>
			</a>
			SWG-14658
		</td>
		<td>
			<a href="https://www.sparkfun.com/products/9434">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/3/1/0/7/09434-03.jpg" alt="Bluetooth USB Module Mini"></center>
				<h3 class="title">Bluetooth USB Module Mini</h3>
			</a>
			WRL-09434
		</td>
	</tr>
	<tr>
		<td>
			<a href="https://www.sparkfun.com/products/17264">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/1/6/2/6/9/17264-SN30_Pro_Bluetooth_GamepadSN30_Pro_Bluetooth_Gamepad-01.jpg" alt="8BitDo SN30 Pro Bluetooth Gamepad"></center>
				<h3 class="title">8BitDo SN30 Pro Bluetooth Gamepad</h3>
			</a>
			WIG-17264
		</td>
	</tr>
</table>


<div class="grid cards" markdown>

-   <a href="https://www.sparkfun.com/products/16905">**USB 2.0 Type-C Cable - 1 Meter**<br>
	CAB-16905

	---

	<figure markdown>
	![USB 2.0 Type-C Cable - 1 Meter](https://cdn.sparkfun.com/assets/parts/1/5/8/3/4/16905-USB_-_C_to_C_cable-01.jpg)
	</figure>
	<figcaption>(Coming Soon)</figcaption>
	</a>

-   <a href="https://www.sparkfun.com/products/21870">**USB A (Female) to Type C (Male) Converter**<br>
	COM-21870

	---

	<figure markdown>
	![USB A (Female) to Type C (Male) Converter](https://cdn.sparkfun.com/assets/parts/2/1/7/0/0/21870-_PRT-_01.jpg)
	</figure>
	</a>

-   <a href="https://www.sparkfun.com/products/14658">**SparkFun USB Thumb Drive (16GB)**<br>
	SWG-14658

	---

	<figure markdown>
	![SparkFun USB Thumb Drive (16GB)](https://cdn.sparkfun.com/assets/parts/1/2/8/5/0/14658-SparkFun_USB_Thumb_Drive__16GB_-01.jpg)
	</figure>
	</a>

-   <a href="https://www.sparkfun.com/products/9434">**Bluetooth USB Module Mini**<br>
	WRL-09434

	---

	<figure markdown>
	![Bluetooth USB Module Mini](https://cdn.sparkfun.com/assets/parts/3/1/0/7/09434-03.jpg)
	</figure>
	</a>

-   <a href="https://www.sparkfun.com/products/17264">**8BitDo SN30 Pro Bluetooth Gamepad**<br>
	WIG-17264

	---

	<figure markdown>
	![8BitDo SN30 Pro Bluetooth Gamepad](https://cdn.sparkfun.com/assets/parts/1/6/2/6/9/17264-SN30_Pro_Bluetooth_GamepadSN30_Pro_Bluetooth_Gamepad-01.jpg)
	</figure></a>

</div>

### Jumper Modification
<p>To modify the jumpers, users will need <a href="https://www.sparkfun.com/categories/49">soldering equipment</a> and/or a <a href="https://www.sparkfun.com/categories/379">knife</a>.</p>


<table class="pdf" style="border-style:none">
	<tr>
		<td>
			<a href="https://www.sparkfun.com/products/9325">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/2/8/7/3/09325_9161-Solder_Lead_Free_-_100-gram_Spool-01.jpg" alt="Solder Lead Free - 100-gram Spool"></center>
				<h3 class="title">Solder Lead Free - 100-gram Spool</h3>
			</a>
			TOL-09325
		</td>
		<td>
			<a href="https://www.sparkfun.com/products/14228">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/1/2/1/7/3/14228-01.jpg" alt="Weller WLC100 Soldering Station">
				</center>
				<h3 class="title">Weller WLC100 Soldering Station</h3>
			</a>
			TOL-14228
		</td>
		<td>
			<a href="https://www.sparkfun.com/products/14579">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/1/2/7/2/5/14579-Chip_Quik_No-Clean_Flux_Pen_-_10mL-01.jpg" alt="Chip Quik No-Clean Flux Pen - 10mL">
				</center>
				<h3 class="title">Chip Quik No-Clean Flux Pen - 10mL</h3>
			</a>
			TOL-14579
		</td>
		<td>
			<a href="https://www.sparkfun.com/products/9200">
				<center><img src="https://cdn.sparkfun.com/r/140-140/assets/parts/2/6/4/6/09200-Hobby_Knife-01.jpg" alt="Hobby Knife">
				</center>
				<h3 class="title">Hobby Knife</h3>
			</a>
			TOL-09200
		</td>
	</tr>
</table>


<div class="grid cards" markdown>

-   <a href="https://www.sparkfun.com/products/9325">**Solder Lead Free - 100-gram Spool**<br>
	TOL-09325

	---

	<figure markdown>
	![Solder Lead Free - 100-gram Spool](https://cdn.sparkfun.com/assets/parts/2/8/7/3/09325_9161-Solder_Lead_Free_-_100-gram_Spool-01.jpg)
	</figure></a>

-   <a href="https://www.sparkfun.com/products/14228">**Weller WLC100 Soldering Station**<br>
	TOL-14228

	---
	
	<figure markdown>
	![Weller WLC100 Soldering Station](https://cdn.sparkfun.com/assets/parts/1/2/1/7/3/14228-01.jpg)
	</figure></a>


-   <a href="https://www.sparkfun.com/products/14579">**Chip Quik No-Clean Flux Pen - 10mL**<br>
	TOL-14579

	---

	<figure markdown>
	![Chip Quik No-Clean Flux Pen - 10mL](https://cdn.sparkfun.com/assets/parts/1/2/7/2/5/14579-Chip_Quik_No-Clean_Flux_Pen_-_10mL-01.jpg)
	</figure></a>


-   <a href="https://www.sparkfun.com/products/9200">**Hobby Knife**<br>
	TOL-09200

	---

	<figure markdown>
	![Hobby Knife](https://cdn.sparkfun.com/assets/parts/2/6/4/6/09200-Hobby_Knife-01.jpg)
	</figure>
	</a>
</div>


!!! tip
	New to jumper pads? Check out our [Jumper Pads and PCB Traces Tutorial](https://learn.sparkfun.com/tutorials/664) for a quick introduction!
	<p align="center">
		<a href="https://learn.sparkfun.com/tutorials/664">How to Work with Jumper Pads and PCB Traces<br>
		<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/6/4/PCB_TraceCutLumenati.jpg"></a>
	</p>


## Suggested Reading

As a more sophisticated product, we will skip over the more fundamental tutorials (i.e. [**Ohm's Law**](https://learn.sparkfun.com/tutorials/voltage-current-resistance-and-ohms-law) and [**What is Electricity?**](https://learn.sparkfun.com/tutorials/what-is-electricity)). However, below are a few tutorials that may help users familiarize themselves with various aspects of the board.


<table class="pdf" style="border-style:none">
	<tr>
		<td align="center">
			<a href="https://learn.sparkfun.com/tutorials/1167">Arduino Shields v2<br>
			<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/1/1/6/7/qwiic_shield.jpg"></a>
		</td>
		<td align="center">
			<a href="https://learn.sparkfun.com/tutorials/61">Installing the Arduino IDE<br>
			<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/1/arduinoThumb.jpg"></a>
		</td>
		<td align="center">
			<a href="https://learn.sparkfun.com/tutorials/15">Installing an Arduino Library<br>
			<img src="https://cdn.sparkfun.com/c/264-148/assets/b/e/4/b/2/50f04b99ce395fd95e000001.jpg"></a>
		</td>
	</tr>
	<tr>
		<td align="center">
			<a href="https://learn.sparkfun.com/tutorials/5">How to Solder: Through-Hole Soldering<br>
			<img src="https://cdn.sparkfun.com/c/264-148/assets/e/3/9/9/4/51d9fbe1ce395f7a2a000000.jpg"></a>
		</td>
		<td align="center">
			<a href="https://learn.sparkfun.com/tutorials/664">How to Work with Jumper Pads and PCB Traces<br>
			<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/6/4/PCB_TraceCutLumenati.jpg"></a>
		</td>
	</tr>
	<tr>
		<td align="center">
			<a href="https://learn.sparkfun.com/tutorials/62">Logic Levels<br>
			<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/2/Input_Output_Logic_Level_Tolerances_tutorial_tile.png"></a>
		</td>
		<td align="center">
			<a href="https://learn.sparkfun.com/tutorials/16">Serial Peripheral Interface (SPI)<br>
			<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/1/6/spiThumb_Updated.jpg"></a>
		</td>
	</tr>
</table>


<div class="grid cards" markdown align="center">

-   <a href="https://learn.sparkfun.com/tutorials/1167">**Arduino Shields v2**

	---

	<figure markdown>
	![Arduino Shields v2](https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/1/1/6/7/qwiic_shield.jpg)
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

-   <a href="https://learn.sparkfun.com/tutorials/5">**How to Solder: Through-Hole Soldering**

	---
	
	<figure markdown>
	![How to Solder: Through-Hole Soldering](https://cdn.sparkfun.com/c/264-148/assets/e/3/9/9/4/51d9fbe1ce395f7a2a000000.jpg)
	</figure></a>

-   <a href="https://learn.sparkfun.com/tutorials/664">**How to Work with Jumper Pads and PCB Traces**

	---
	
	<figure markdown>
	![How to Work with Jumper Pads and PCB Traces](https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/6/4/PCB_TraceCutLumenati.jpg)
	</figure></a>

-   <a href="https://learn.sparkfun.com/tutorials/62">**Logic Levels**

	---
	
	<figure markdown>
	![Logic Levels](https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/2/Input_Output_Logic_Level_Tolerances_tutorial_tile.png)
	</figure></a>

-   <a href="https://learn.sparkfun.com/tutorials/16">**Serial Peripheral Interface (SPI)**

	---
	
	<figure markdown>
	![Serial Peripheral Interface (SPI)](https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/1/6/spiThumb_Updated.jpg)
	</figure></a>
</div>
## Board Dimensions
The board dimensions are illustrated in the drawing below; the listed measurements are in inches.


<figure markdown>
[![Board Dimensions](./assets/img/hardware/dimensions.png "Click to enlarge"){ width="400" }](./assets/img/hardware/dimensions.png)
<figcaption markdown>Board dimensions ([PDF](./assets/board_files/dimensions.pdf)) for the USB Host Shield, in inches.</figcaption>
</figure>

??? tip "Need more measurements?"
	For more information about the board's dimensions, users can download the [**Eagle files**](./assets/board_files/eagle_files.zip) for the board. These files can be opened in Eagle and additional measurements can be made with the dimensions tool.

	??? info ":octicons-download-16:{ .heart } Eagle - Free Download!"
		Eagle is a [CAD]("computer-aided design") program for electronics that is free to use for hobbyists and students. However, it does require an account registration to utilize the software.

		<center>
		[Download from<br>:autodesk-primary:{ .autodesk }](https://www.autodesk.com/products/eagle/free-download "Go to downloads page"){ .md-button .md-button--primary width="200px" }
		</center>

	??? info ":straight_ruler: Dimensions Tool"
		This video from Autodesk demonstrates how to utilize the dimensions tool in Eagle, to include additional measurements:

		<center>

		<div class="video">
		<iframe src="https://www.youtube.com/embed/dZLNd1FtNB8" title="EAGLE Dimension Tool" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

		![QR code to instructional video](./assets/img/qr_code/dimension_tool.png){ .qr width=100 }
		</div>

		</center>


## Power
The MAX3421E USB controller only requires **3.3V** to operate; however, the shield *(and USB-C connector)* is powered entirely through either the `5V` or `VIN` pins of the connected Arduino board.

<figure markdown>
[![Power connections](./assets/img/hardware/power_connections.jpg "Click to enlarge"){ width="400" }](./assets/img/hardware/power_connections.jpg)
<figcaption markdown>USB Host Shield power connections.</figcaption>
</figure>

Below, is a general summary of the power circuitry on the board:

* **`VIN`** - Provides a regulated 3.3V and 5V for the shield
	* To utilize this pin, users will need to connect an external power source to the barrel jack of the Arduino board they are using.
* **`5V`** - Provides 5V and a regulated 3.3V for the shield
* **`GND`** - The common ground or the 0V reference for the voltage supplies.
* _**`VBUS`** - The voltage to the USB-C connector (**5V**)_
	* In reference to the `VBUS` net of the [schematic](./assets/board_files/schematic.pdf).
	* The available current is limited to what is supplied from the `VIN`/`5V` pin, up to the 750 mA threshold of the thermal fuse.

	!!! info
		When a PD device is connected and the voltage output drops below **4.75V**, the PD device will restrict its current draw to avoid potentially damaging the DFP *(downward-facing port)*.

*For more details, users can reference the [schematic](./assets/board_files/schematic.pdf) and the [datasheets of the individual components](../resources/#hardware-component-documentation) in the power circuitry.*


### Power LED
The red, power (`PWR`) LED will light up once **5V** is supplied to the shield. For most users, it will light up when power is supplied to the connected Arduino board.

<figure markdown>
[![Power LED](./assets/img/hardware/LED_pwr.jpg "Click to enlarge"){ width="400" }](./assets/img/hardware/LED_pwr.jpg)
<figcaption markdown>USB Host Shield `PWR` status LED indicator.</figcaption>
</figure>


### Power Switches
There are two switches on the USB Host Shield. One provides a selectable power input for the shield *(`VIN` or `5V`)* and the other provides power control *(on/off)* to the shield and USB connector.

<figure markdown>
[![Switches](./assets/img/hardware/switches.jpg "Click to enlarge"){ width="400" }](./assets/img/hardware/switches.jpg)
<figcaption markdown>Power switches on the USB Host Shield.</figcaption>
</figure>

* Power Select<br>
	The power select switch allows users to easily choose the power supply for the shield. This switch mostly controls how the regulated 5V output for the USB-C connector is sourced. However, both options additionally supply the regulated 3.3V for the MAX3421E USB controller.
	* **VIN** - Draws power through the Arduino board's `VIN` pin
		* Provides a regulated 5V output to the USB-C connector from the `VIN` pin, which is separate/isolated from the `5V` pin of the Arduino board
		* Provides a regulated 3.3V output for the MAX3421E USB controller from the regulated 5V output of the `VIN` pin
	* **5V** - Draws power through the Arduino board's `5V` pin
		* Provides a 5V output to the USB-C connector from the `5V` pin of the Arduino board
		* Provides a regulated 3.3V output for the MAX3421E USB controller from the `5V` pin
* Main Power<br>
	The main power switch controls the power input to the shield. This switch turns the shield **on** or **off**; when off, the power output to the USB-C connector is also disabled.


### USB-C Connector
??? info "Charging PD Devices"
	When a PD device is connected and the voltage output drops below **4.75V**, the PD device will restrict its current draw to avoid potentially damaging the DFP *(downward-facing port)*.

The USB-C port supports limited power output at **5V**. The available current is limited to what is supplied to the shield from either the `VIN` or `5V` pin, up to the **750 mA** threshold of the thermal fuse.

<figure markdown>
[![USB power](./assets/img/hardware/usb_connector.jpg "Click to enlarge"){ width="400" }](./assets/img/hardware/usb_connector.jpg)
<figcaption markdown>USB-C connector on the USB Host Shield.</figcaption>
</figure>



## USB Controller
The [MAX3421E](./assets/component_documentation/MAX3421E.pdf) from [Maxim Integrated *(now part of Analog Devices)*](https://www.maximintegrated.com/), is a USB peripheral/host controller that can be implemented as a full-speed USB peripheral or a full-/low-speed host compliant *(USB specification rev 2.0)*. This allows for a vast collection of USB peripherals to be interfaced with an embedded system. The MAX3421E also includes eight general-purpose inputs and outputs so users can reclaim the I/O pins used for the SPI interface and gain additional ones.

<center>
<table>
	<tr>
		<td>
			<H3>Features</H3>
			<hr>
			<ul>
				<li>Provides USB Host and Peripheral Functionality
					<ul>
						<li>USB 2.0 Specification: 12 Mbps <i>(full-speed)</i></li>
						<li>16MB of Embedded SPI Flash Storage</li>
					</ul>
				</li>
				<li>Operating Voltage: 3.0 - 3.6 V</li>
				<li>Supply Current:
					<ul>
						<li>45 mA <i>(max)</i></li>
						<li>8.7 mA <i>(idle)</i></li>
						<li>30 - 60 &micro;A <i>(suspend)</i></li>
					</ul>
				</li>
				<li>SPI Clock Speed: 0 - 26 MHz</li>
				<li>Operating Temperature: -40 - +85 °C</li>
			</ul>
		</td>
		<td align="center">
			<a href=".././assets/img/hardware/MAX3421E.jpg"><img alt="MAX3421E chip" title="Click to enlarge" src=".././assets/img/hardware/MAX3421E.jpg" width="300"></a><br>
			<i>MAX3421E chip on the USB-C Host Shield.</i>
		</td>
	<tr>
</table>
</center>


### I/O Pins
The MAX3421E is controlled with seven pins on the USB-C Host Shield. Additionally, the MAX3421E provides eight general-purpose inputs and outputs for users to reclaim their I/O pins and gain additional ones.

<div class="grid cards" markdown>

-	<figure markdown>
	[![](./assets/img/hardware/io_shield.jpg "Click to enlarge"){ width="300" }](./assets/img/hardware/io_shield.jpg)
	<figcaption markdown>I/O pins used by the USB Host Shield.</figcaption>
	</figure>

-	=== "SPI Pins"

		* SCK: `D13`
		* POCI: `D12`
		* PICO: `D11`
		* CS: `D10`

	===	"I/O Pins"

		* INT: `D9`
		* GPX: `D8`
		* RST: `D7`

	=== "Power Pins"

		* `VIN`
		* `5V`
		* `GND`

		??? info
			For more information about the power pins, please refer to the [power section](#power) *(above)*.

</div>

??? tip "New Feature"
	New on this shield, we have added a silkscreen indicator to mark the I/O pins used by the shield. This should help users who are stacking other shields to avoid pin conflicts without referencing the documentation. 

	<figure markdown>
	[![](./assets/img/hardware/shield_pins_marked2.jpg "Click to enlarge"){ width="300" }](./assets/img/hardware/shield_pins_marked.jpg)
	<figcaption markdown>I/O pins that are marked on the USB Host Shield.</figcaption>
	</figure>


#### SPI Pins
??? info "[OSHW](https://www.oshwa.org/) Compliance"
	To comply with the latest [OSHW](https://www.oshwa.org/) design practices, we have [adopted the new SPI signal nomenclature](https://www.sparkfun.com/spi_signal_names) (**SDO**/**SDI** and **PICO**/**POCI**). The terms Master and Slave are now referred to as Controller and Peripheral. The `MOSI` signal on a controller has been replaced with `SDO` or `PICO`. Please refer to this [announcement on the decision to deprecate the **MOSI**/**MISO** terminology and transition to the **SDO**/**SDI** naming convention](https://www.oshwa.org/a-resolution-to-redefine-spi-signal-names).

The MAX3421E operates using a register set, accessed by an SPI interface at speeds up to 26MHz. Any SPI controller can add USB peripheral or host functionality using the simple 3- or 4- wire SPI interface The USB-timed operations are performed inside the MAX3421E with interrupts provided at completion, so any SPI controller does not need timers to meet USB timing requirements. Additionally, the firmware to operate the MAX3421E can also be simplified to only support a specific target device.

<center>
	<table>
		<tr>
			<td style="vertical-align:middle;">
				<table>
					<tr>
						<th style="text-align:center">SCK</th>
						<td style="text-align:center"><code>D13</code> (<code>SCK</code>)</td>
					</tr>
					<tr>
						<th style="text-align:center">SDI or POCI</th>
						<td style="text-align:center"><code>D12</code> (<code>MISO</code>)</td>
					</tr>
					<tr>
						<th style="text-align:center">SDO or PICO</th>
						<td style="text-align:center"><code>D11</code> (<code>MOSI</code>)</td>
					</tr>
					<tr>
						<th style="text-align:center">CS</th>
						<td style="text-align:center"><code>D10</code> (<code>SS</code>)</td>
					</tr>
				</table>
			</td>
			<td align="center">
				<a href=".././assets/img/hardware/pins_spi.jpg"><img alt="Annotated image of SPI pins" title="Click to enlarge" src=".././assets/img/hardware/pins_spi.jpg" width="300"></a>
				<br>
				<i>Default SPI bus connections on the USB Host Shield.</i>
			</td>
		</tr>
	</table>
</center>

??? tip
	To learn more about the serial peripheral interface (SPI) protocol, check out this great <a href="https://learn.sparkfun.com/tutorials/serial-peripheral-interface-spi">tutorial</a>.
	<p align="center">
		<a href="https://learn.sparkfun.com/tutorials/16">Serial Peripheral Interface (SPI)<br>
		<img src="https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/1/6/spiThumb_Updated.jpg"></a>
	</p>

#### I/O Pins
In addition to the SPI pins, there are three I/O pins for the MAX3421E.

<center>
	<table>
		<tr>
			<td style="vertical-align:middle;">
					<table>
						<tr>
							<th style="text-align:center">INT</th>
							<td style="text-align:center"><code>D9</code> <code>(Output)</code></td>
						</tr>
						<tr>
							<th style="text-align:center">GPX</th>
							<td style="text-align:center"><code>D8</code> <code>(Output)</code></td>
						</tr>
						<tr>
							<th style="text-align:center">RES</th>
							<td style="text-align:center"><code>D7</code> <code>(Input)</code></td>
						</tr>
					</table>
			</td>
			<td align="center">
				<a href=".././assets/img/hardware/pins_io.jpg"><img alt="Annotated image of IO pins" title="Click to enlarge" src=".././assets/img/hardware/pins_io.jpg" width="300"></a>
				<br>
				<i>I/O pins on the USB Host Shield.</i>
			</td>
		</tr>
	</table>
</center>


* `INT` - Interrupt (Output)

	The MAX3421E `INT` pin outputs a signal when a USB event occurs, which requires the attention of the SPI controller. In level mode, the `INT` pin is open-drain and active low. In edge mode, the pin can be operated as push-pull output with programmable polarity. Users can enable the interrupt by setting the IE bit in the CPUCTL (R16) register. The `INT` pin can also be configured to be triggered from the general-purpose inputs (`GPIN0`–`GPIN7`).

* `GPX` - General-Purpose Multiplexed (Output)
	
	The MAX3421E `GPX` pin indicates one of five internal signals:

	* `OPERATE` - The signal is high when the MAX3421E is able to operate after a power-up or `RES` reset.
	* `VBUS_DET` - Provides the `VBCOMP` comparator output.
	* `BUSACT` - The signal is active (high), whenever there is traffic on the USB bus.
	* `INIRQ` -  In this mode, `GPIN` interrupts appear only on the `GPX` pin, and do not appear on the `INT` output pin.
		* When the SEPIRQ bit of the MODE (R27) register is set high, the `BUSACT` signal is removed 
	* `SOF` - A square wave is produced, with a positive edge that indicates the USB start-of-frame.

	The internal MAX3421E signal that appears on `GPX` is programmable by writing to the `GPXB` and `GPXA` bits of the PINCTL (R17) register and the `SEPIRQ` bit of the MODE (R27) register. 

	<center>

	| GPXB | GPXA | GPX PIN OUTPUT |
	|:-:|:-:|:-:|
	| 0 | 0 | OPERATE (Default State) |
	| 0 | 1 | VBUS_DET |
	| 1 | 0 | BUSACT/INIRQ |
	| 1 | 1 | SOF |
	
	</center>

* `RES` - Device Reset (Input)

	Driving the `RES` pin low causes a chip reset on the MAX3421E. In a chip reset, all registers are reset to their default states, except for PINCTL (R17), USBCTL (R15), and SPI logic. To bring the MAX3421E out of chip reset, `RES` must be driven high.

	!!! note
		The MAX3421E is internally reset if either V<sub>CC</sub> or V<sub>L</sub> is not present. The register file is not accessible under these conditions.


#### MAX3421E I/O Pins
The MAX3421E also includes eight general-purpose inputs (8) and outputs (8), that can be used to reclaim the I/O pins used for the SPI interface and gain additional ones.

* `GPOUT#` - General-Purpose Push-Pull Outputs.
* `GPIN#` - General-Purpose Inputs.
	* `GPIN7`–`GPIN0` are connected to V<sub>L</sub> with internal pullup resistors.

<figure markdown>
[![Annotated image of GPIO pins](./assets/img/hardware/pins_gpio.jpg "Click to enlarge"){ width="400" }](./assets/img/hardware/pins_gpio.jpg)
<figcaption markdown>GPIO pins on the USB Host Shield.</figcaption>
</figure>

### USB-C Connector
??? info "Charging PD Devices"
	When a PD device is connected and the voltage output drops below **4.75V**, the PD device will restrict its current draw to avoid potentially damaging the DFP *(downward-facing port)*.

The USB-C connector is used to provide provided an interface to the MAX3421 USB controller, which can function as either a USB peripheral or host. It also supports limited power output at **5V**. The available current is limited to what is supplied to the shield from either the `VIN` or `5V` pin, up to the **750 mA** threshold of the thermal fuse.

<figure markdown>
[![USB-C Connector](./assets/img/hardware/usb_connector.jpg "Click to enlarge"){ width="400" }](./assets/img/hardware/usb_connector.jpg)
<figcaption markdown>USB-C connector on the USB Host Shield.</figcaption>
</figure>


## Reset Button
Sometimes, an Arduino shield covers the ++"Reset"++ button of a user's Arduino board; therefore, a ++"Reset"++ button is provided on the USB-C Host shield. This allows users to easily reset their Arduino board without having to squeeze in between the Arduino board and shield to hit the button.

<figure markdown>
[![Reset Button](./assets/img/hardware/button_reset.jpg "Click to enlarge"){ width="400" }](./assets/img/hardware/button_reset.jpg)
<figcaption markdown>++"Reset"++ button and `RST` pin on the USB Host Shield.</figcaption>
</figure>

!!! note
	The reset button (`RST` pin) is different from the `RES` (reset) pin for the MAX3421E.
	
	* The button, `RST` pin on the shield, resets the microcontroller of the attached development board.
	* The `RES` pin, connected to pin `7` on the shield, is a chip reset for the MAX3421E.


## Jumper
There is a **SHLD** jumper on the top of the board that can be used to easily disconnect the shroud of the USB-C connector from `GND`.

??? tip "New to jumper pads?"
	Check out our [Jumper Pads and PCB Traces Tutorial](https://learn.sparkfun.com/tutorials/664) for a quick introduction!

	<div class="grid cards col-4" markdown align="center">

	-   <a href="https://learn.sparkfun.com/tutorials/664">
		<figure markdown>
		![Tutorial thumbnail](https://cdn.sparkfun.com/c/264-148/assets/learn_tutorials/6/6/4/PCB_TraceCutLumenati.jpg)
		</figure>

		---
		
		**How to Work with Jumper Pads and PCB Traces**</a>

	</div>

<figure markdown>
[![Jumpers](./assets/img/hardware/jumper.jpg "Click to enlarge"){ width="400" }](./assets/img/hardware/jumper.jpg)
<figcaption markdown>The `SHLD` jumper on the top of the USB Host Shield.</figcaption>
</figure>
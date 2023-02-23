!!! warning "Need Help?"
    If you need technical assistance or more information on a product that is not working as you expected, we recommend heading on over to the [SparkFun Technical Assistance](https://www.sparkfun.com/technical_assistanc) page for some initial troubleshooting.

    <center>
    [SparkFun Technical Assistance Page](https://www.sparkfun.com/technical_assistance){ .md-button .md-button--primary }
    </center>
    
    If you can't find what you need there, the [SparkFun Forums](https://forum.sparkfun.com/index.php) is a great place to search for additional information and to ask questions.
    
    !!! info "Account Registration Required"
        If this is your first visit to our forum, you'll need to [register an account](https://forum.sparkfun.com/ucp.php?mode=register) to post questions.


## Initialization Failure
The following error message, in the serial terminal, indicates that there was a problem communicating with the MAX3421E chip.

>   ```
    OSC did not start
    ```

This error occurs here in the example code:

>   ```c++
    if (Usb.Init() == -1)
        Serial.println("OSC did not start.");
    ```

Here are a few steps users can perform to diagnose the issue:

* Double-check the hardware connections; including, but not limited to the solder joints, header pins (male and female), etc.
    * Disconnect power from the board and try a continuity test with a multimeter.
* Make sure the switches are in the correct position to provide power to the shield.
    * The shield requires a minimum 5V input voltage.
    * The red, power LED should be lit when the shield is powered.
* Double-check the library for any [I/O pin modifications](../software_overview/#io-pin-modifications).

## USB Hub
If users connect [USB hubs](https://en.wikipedia.org/wiki/USB_hub) or USB cables with a hub to the USB host shield, refer to the [hub_demo](https://github.com/felis/USB_Host_Shield_2.0/tree/master/examples/hub_demo) example from the [USB_Host_Shield_2.0 Arduino library](https://github.com/felis/USB_Host_Shield_2.0). This example can be found in the **File** dropdown menu _(i.e. **File** > **Examples** > **USB Host Shield Library 2.0** > **hub_demo**)_ and will list the USB description for the hub(s) and all the peripheral devices connected to the hub(s).

!!! info "Only interested in the USB hub description?"
    To see just the USB description for the hub(s) connected to the USB host shield, follow the information in the [library's FAQ](https://github.com/felis/USB_Host_Shield_2.0#faq). Utilizing the [USB_dec](https://github.com/felis/USB_Host_Shield_2.0/tree/master/examples/USB_desc) example, uncomment [lines 12-18](https://github.com/felis/USB_Host_Shield_2.0/blob/master/examples/USB_desc/USB_desc.ino#L12-L18)(1).
    { .annotate }

    1. Each instance of `#!c++ USBHub  Hub<number>(&Usb);` enables a USB hub, but the library is limited up to **seven** USB hubs. 

    ``` c++ linenums="11" hl_lines="2-8" title="USB_desc.ino"
    --8<-- "https://raw.githubusercontent.com/felis/USB_Host_Shield_2.0/master/examples/USB_desc/USB_desc.ino:11:19"
    ```
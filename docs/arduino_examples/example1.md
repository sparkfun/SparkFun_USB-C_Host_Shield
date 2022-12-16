## USB Description
For our first example, we will be utilizing the [USB_dec](https://github.com/felis/USB_Host_Shield_2.0/tree/master/examples/USB_desc) example from the [USB_Host_Shield_2.0 Arduino library](https://github.com/felis/USB_Host_Shield_2.0). This example can be found in the File dropdown menu _(i.e. **File** > **Examples** > **USB Host Shield Library 2.0** > **USB_Desc**)_. Once the example has been opened, users should see two files `USB_desc.ino` and `pgmstrings.h`.

??? note "Example Files"
    === "USB_desc.ino"

        ```
        --8<-- "https://raw.githubusercontent.com/felis/USB_Host_Shield_2.0/master/examples/USB_desc/USB_desc.ino"
        ```

    === "pgmstrings.h"
    
        ```
        --8<-- "https://raw.githubusercontent.com/felis/USB_Host_Shield_2.0/master/examples/USB_desc/pgmstrings.h"
        ```

Users will need to connect a device to the USB-C connector before running the example. After the example executes, users should see an output in the [Serial Monitor](https://learn.sparkfun.com/tutorials/112) with the USB description of the connected device.
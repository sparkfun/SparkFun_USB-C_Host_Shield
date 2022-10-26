!!! note
    <p><span class="glyphicon glyphicon-question-sign" aria-hidden="true"></span> <strong>Not working as expected and need help? </strong></p>
    <p>If you need technical assistance and more information on a product that is not working as you expected, we recommend heading on over to the <a href="https://www.sparkfun.com/technical_assistance">SparkFun Technical Assistance</a> page for some initial troubleshooting.</p>
    <center>
    [SparkFun Technical Assistance Page](https://www.sparkfun.com/technical_assistance){ .md-button .md-button--primary }
    </center>
    <p>If you can't find what you need there, you'll need a <a href="https://forum.sparkfun.com/ucp.php?mode=register">Forum Account</a> to search product forums and post questions.<p>

### Enable debugging

By default serial debugging is disabled in the Arduino library. To turn it on simply change `ENABLE_UHS_DEBUGGING` to `1` in the [settings.h](https://github.com/felis/USB_Host_Shield_2.0/blob/master/settings.h#L42) file:

```C++
#define ENABLE_UHS_DEBUGGING 1
```
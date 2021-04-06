# Equipment

<center style="color: red; font-weight: bold">
<p><b>This is very very important.</b></p>


<p><i>You must get very specific USB “chargers” (power supplies) and cables.  {And SD card?}  We list below the ones that have worked.  If you do not, the Raspberry Pi can (and probably will) randomly lock up, crash.  The cause will look mysterious.</i></p>
</center>

Why?  The escape pod is running software that demands a lot of a Raspberry Pi
at times.  The Raspberry Pi has requirements higher than standard
USB-specification chargers and cables.  The Pi will have errors and random
crashes if the right ones are not used.


## Hardware Configurations

If you are buying hardware

*   Buy the Raspberry Pi 4, with the official Charger.  Raspberry PI 4 in 2GB,
    4GB, and 8GB are all reported to work.   (Prices vary, but the 8GB Pi 4,
    charger, and SD card cost me $81 at Micro center.  Another $6 for the
    optional micro hdmi cable)
*   A Canakit charger may be instead  (see below for links).

If you already have a Raspberry PI 3B+, this can be used.  However be aware:

*   The PI3 will be noticeably slower and less responsive 
*   Make absolutely sure to get very specific power supplies and cables.  Power
    supplies and cables that worked with other software on a Pi 3 may not work
    here.  The EscapePod software has higher demands than raspbian.  Without
    the specific supplies AND cables, there may be power issues: random
    crashes, lock ups, and confusing error messages.
*   Prefer power supplies where the cable is directly built-in (connected)
    rather than a separate charger and a cable.  Like this:


![](image1.jpg#center)
_Figure: This is what a Raspberry Pi power supply should look like_


Pi3  'official’ Chargers (tested with a Pi3)

*   [https://shop.pimoroni.com/products/raspberry-pi-universal-power-supply](https://shop.pimoroni.com/products/raspberry-pi-universal-power-supply)	

Other chargers tested with Pi3


*   RavPower 4 and [Exact name of cable.]
*   CanaKit USB-C Raspberry Pi 4 Power Supply: [https://www.amazon.com/gp/product/B07TYQRXTK/](https://www.amazon.com/gp/product/B07TYQRXTK/)

Pi4 official USB-C Chargers 

*   [https://shop.pimoroni.com/products/raspberry-pi-official-usb-c-power-supply?variant=29157000085587](https://shop.pimoroni.com/products/raspberry-pi-official-usb-c-power-supply?variant=29157000085587)


## Sundry Tips

From the internet: "If your Raspberry Pi 4 is running a little hot, users can
get it running cooler simply by positioning it vertically with the GPIO header
at the bottom and the power and HDMI ports at the top."

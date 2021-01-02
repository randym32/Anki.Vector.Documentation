# Pi Network Troubleshooting

This is a page for troubleshooting the EscapePod software set up.
See also

* [Pi equipment](../escape pod/equipment.md) for information about the Raspberry Pi
  and charger that you will need
* [Pi issues](Pi issues.md) for information related to troubleshooting the Pi
  hardware
* [Troubleshooting the EscapePod software setup](EscapePod setup.md), especially adding licenses.


## Symptoms of Network and Wifi Connectivity issues

Symptoms: The Raspberry Pi is connected to the network, but sometimes is
unavailable; it appears to drop off.
Fixes:

* Use wired ethernet if possible
* If using Wifi:
    - use only 2.5GHz -- remove the your 5GHz Wifi access points
      from the list.
    - Check that the WiFi configuration file syntax is correct
    - Don't forget to reboot twice
    - If using HDMI, reduce the resolution 
    - Update the firmware
* Check the Router DHCP lease time; give a static/fixed IP address if possible

The following will help diagnose specific problems.

<a name="ping-test"></a>
### First Steps: The Ping test
First, double check that the Raspberry Pi is powered on, it's red LED is on.

Can you ping the EscapePod:

Try 

    ping escapepod.local

If you are able to ping using this step, the EscapePod is on the network, and 
mDNS is working.   Go to Step TBD

Try 

    ping escapepod.lan

Try 

    ping escapepod.box

Try

    ping escapepod

If you are able to ping using either of these two steps, the EscapePod is on
the network, but there is a problem with mDNS.  Go to step [mDNS issues](#mDNS).

If you know the address for the escapepod, trying pinging it.
If you can ping it, the issue is with mDNS.  Go to step [mDNS issues](#mDNS).

Otherwise your LAN or WiFi connection is not working.  If you are using a
ethernet LAN cable, check that it is fully plugged into the Pi and your router.
If you are using WiFi, go to the next secton.i


<a name="wifi"></a>
## Wifi Issues

Troubleshooting the Wifi.
Note: this section does not apply if you are using an ethernet cable between your
router and the escape pod.

If possible, it is recommended to use an ethernet cable -- at least until the
EscapePod has been setup on your network and any other possible issues are
resolved.

###  Did not reboot enough times after setting up the network config (ie config file not transferred to main linux)

Unplug the power from the raspberry pi.
Plug the power in and give it a few minutes.
Unplug the power from the raspberry pi _again_.
Plug the power in and give it a few minutes.
Repeat the [ping test](#ping-test) above.


### Wifi config file typo/syntax error

It is possible that there is a typo in the wifi networking configuration file.
Take the SD card out, and put it into your computer.  Open the configuration
file and double check that it looks right:

* Does it have the right spacing?
* Does the wifi Access Point name match the name of your Wifi?
  Any typos?
* Is the password the right one for your Wifi? Any typos?


### Use 2.5GHz instead of 5GHz Wifi

The Raspberry Pi 3 doesn't work with 5GHz

The Raspberry Pi 4 is "internet reported" to be flaky with 5GHz, and
periodically drop off.

### HDMI Interference

If you are having network connectivity issues -- the WiFi works for a while
then drops out -- it may be the HDMI.
High resolution mode HDMI generates enough noise to wreck WiFi on Pi 4.

Fixes:

*   Don't use HDMI so high of resolution
*   Don't use 5Ghz
*   Try updatign the firmware


#### Updating the Raspberry Pi firmware.
A firmware update can fix some of the HDMI interference.  Here is how I updated
it.  As a first step I installed "rpi-eeprom-update" to list the current
installed firmware, but it may have updated it on me (it was that or when I did
an ubuntu update).

The following installation steps are from:
[https://askubuntu.com/questions/1253070/raspberry-pi-4-firmware-upgrade-eeprom-over-ubuntu-20-04](https://askubuntu.com/questions/1253070/raspberry-pi-4-firmware-upgrade-eeprom-over-ubuntu-20-04)

    curl -O http://ports.ubuntu.com/pool/universe/r/raspberrypi-userland/libraspberrypi0_0~20200520+git2fe4ca3-0ubuntu2_arm64.deb
    sudo apt install ./libraspberrypi0_0~20200520+git2fe4ca3-0ubuntu2_arm64.deb
    curl -O http://ports.ubuntu.com/pool/universe/r/raspberrypi-userland/libraspberrypi-bin_0~20200520+git2fe4ca3-0ubuntu2_arm64.deb
    sudo apt install ./libraspberrypi-bin_0~20200520+git2fe4ca3-0ubuntu2_arm64.deb
    sudo add-apt-repository ppa:waveform/eeprom
    sudo apt update
    apt list --upgradable

After doing that (I had to do it several times to complete all of the myriads of updates)
this is what I saw:

    BCM2711 detected
    VL805 firmware in bootloader EEPROM
    *** UPDATE AVAILABLE ***
    BOOTLOADER: update available
    CURRENT: Thu Mar 19 14:27:25 UTC 2020 (1584628045)
     LATEST: Thu Sep  3 12:11:43 UTC 2020 (1599135103)
     FW DIR: /lib/firmware/raspberrypi/bootloader/critical
    VL805: up-to-date
    **CURRENT: 000137ad**
    ** LATEST: 000137ad**

A day later (with the unexplained firmware update):

    sudo rpi-eeprom-update

    BCM2711 detected
    VL805 firmware in bootloader EEPROM
    BOOTLOADER: up-to-date
    CURRENT: Thu Sep  3 12:11:43 UTC 2020 (1599135103)
     LATEST: Thu Sep  3 12:11:43 UTC 2020 (1599135103)
     FW DIR: /lib/firmware/raspberrypi/bootloader/critical
    VL805: up-to-date
    **CURRENT: 000138a1**
    ** LATEST: 000138a1**

One of those tools I installed gives another way to display the version numbers
(it's what the tool uses):

    vcgencmd bootloader_version | grep timestamp

    sudo lspci -d 1106:3483 -xxx | awk '/^50:/ { print "VL805 FW version: " $5 $4 $3 $2" }

The first displays the bootloader version and the second for the VL805 firmware.
This can useful for identifying if an update is relevant before applying one.


<a name="mDNS"></a>
## mDNS issues

The network name for the escape pod should appear as "escapepod.local"  But it
may also appears as "escapepod" or "escapepod.lan" to your computer.  In that
case you won't be to use the web interface without problems.

There are a few different causes that could be making this happen.
First, check that your computer has the right software installed and 
settings changes made.  See

* [Computer setup](../escape pod/computer setup.md) for information about the
  software to install on your computer, and other adjustments to make mDNs work.

Next, if you're still having trouble, your router may be contributing.
There are too many to know ahead of time their configurations, but we know how
to tweak OpenWRT.

### Router-based issues

One possible source of problems is the router configuration.  Here is what to
look for to see if you have an OpenWRT-based (or Dnsmasq-based) router.
(This section may not apply if you have a different kind of router; there are
too many to know ahead of time their configurations.)

First, go to your network router, and choose the "Network" menu, and then select
"DHCP and DNS" router:

![openWRT](openwrt-1.png#zoom "openWRT")
_Figure: openWRT_

This will open a settings page like the following:

![openWRT local domain settting](openwrt-local.png#zoom "openWRT local domain settting")
_Figure: openWRT local domain settting_

The key thing to look for here is the "Local domain"  In my case the local
domain was set "lan" (possibly by default, or a choice I made long ago).
For some german routers (e.g. from Telekom) may be set to "box".
This setting explains why the name "escapepod.lan" worked. To fix the problem
change the local domain to "local".

Once the change has been made, test it on the router.  Open the "Network" menu
and select "Diagnostics":

![openWRT diagnostics menu item](openwrt-diagnostics.png#zoom "openWRT diagnostics menu item")
_Figure: openWRT diagnostics menu item_

You will get a ping tool on the router:

![openWRT ping tool](openwrt-ping.png#zoom "openWRT ping tool")
_Figure: openWRT ping tool_

Enter "escapepod.local" in the field, click ping.  You should see successful
pings from the escape pod.  If not, there is another problem.


#### IPv6 short lease times causing mDNS Update issues

With my OpenWRT (dnsmasq) router, the  IPv6 lease time defaults to 40 hours
(and it can't be changed).  This may be a cause why the Vector is unable to
find the EscapePod after awhile.  The EscapePod has to renew it's addressing
information and Vector is unable to reach it during the renewal.

The following worked with success for me:

*   Use fixed IP addresses on the router
*   Configured EscapePod to only use 2.5GHz WiFi access points

## SSH related issues

### SSH can not reach the Pi at all

First, follow the steps earlier to be sure that you can ping.

1. Can you ping?  See section [First Steps: The Ping test](#ping-test)
   to perform the basic connectivity tests.

2. Check to see if yu can ssh to the IP address.  
3. Does a message appear on the raspberry Pi console?
   That may indicate how far the connection made it; it may also reveal a power
   issue.  See [Pi issues](Pi issues.md) for diagnosing power issues.

4. Can you log in on the console with a USB kbd and monitor?
   (user name ubuntu, password ubuntu)

### SSH/Putty says it is "out of date: can't exchange keys"

If putty displays a message that says it can't exchange keys, this indicates
you (well, I) have a very old version of putty.  For example:

![Putty out of date error message](putty-error.png#zoom "Putty out of date error message")
_Figure: Putty out of date error message_

The solution is to update ssh / putty.

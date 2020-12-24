# Pi general troubleshooting

This is a page for troubleshooting the Pi hardware.
See also:

* [Pi equipment](../escape pod/equipment.md) for information about the Raspberry Pi
  and charger that you will need
* [Pi connectivity](Pi connectivity.md) to troubleshoot the connection between your
  Pi, network and computer.  This includes Wifi, and mDNS troubleshooting.
* [Troubleshooting the EscapePod software setup](EscapePod setup.md), especially adding licenses.


## Checking the basics

Some potential problems (root causes) to look for:

* The software image is not on the SD card
* The SD card is not in Pi
* The Pi is not  powering on

Connect the Raspberry Pi to a hdmi monitor and power it on.

- Does it show a color gradient in a square when first poered on?

    - Yes: this a good sign.  This is what should happen

    - No -> there is a problem with the power, the SD card, (or maybe the HDMI cable & monitor)
      Check that these are properly connected.  Do you have the right SD card?  Is it flashed?

- Does the Pi show a bunch of text as it boots?

    - Yes: this a good sign.  This is what should happen
    - No -> there is a problem with the power, the SD card, (or maybe the HDMI cable & monitor)
      Check that these are properly connected.  Do you have the right SD card?  Is it flashed?


## Pi Power supply issues

These happen when the power supply doesn’t provide enough power, or the cable
isn’t good enough.

Some potential problems (root causes) to look for:

* Connect the Raspberry Pi to a HDMI monitor and power it on.  Watch for a
 "lightning bolt" in the corner.   If it regularly appears, the power supply or
 cable is the issue.

* Look for text that pops up on the display console with words "under-voltage".

* A common symptom is that the Raspberry Pi may stop responding; or a SSH
 connection may suddenly disconnect.

If you see those, you need to change to your power supply for the Raspberry Pi. See
[Pi equipment](../escape pod/equipment.md) for a list of chargers.

### What else to look for

In /var/log/sys log any lines like the following:

    Dec 11 11:43:37 escapepod kernel: [  994.885094] rpi_firmware_get_throttled: 7 callbacks suppressed
    Dec 11 11:43:37 escapepod kernel: [  994.885103] Voltage normalised (0x00000000)
    Dec 11 11:44:03 escapepod kernel: [ 1021.092573] Under-voltage detected! (0x00050005)
    Dec 11 11:44:07 escapepod kernel: [ 1025.124419] Voltage normalised (0x00000000)

In /var/log/kern.log any lines like the following:

    Dec 11 11:22:58 escapepod kernel: [31302.855548] rpi_firmware_get_throttled: 5 callbacks suppressed
    Dec 11 11:22:58 escapepod kernel: [31302.855559] Under-voltage detected! (0x00050005)
    Dec 11 11:23:02 escapepod kernel: [31306.887532] Voltage normalised (0x00000000)

In /var/log/dmesg any lines like the following:

    [   21.181843] kernel: Under-voltage detected! (0x00050005)

The following text that get displayed on the monitor

    brcmfmac: brcmf_sdio_htclk: HT Avail request error:

If you see those, you need to change to your power supply for the Raspberry Pi. See
[Pi equipment](../escape pod/equipment.md) for a list of chargers.

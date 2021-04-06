# Escape pod setup troubleshooting

This is a page for troubleshooting the EscapePod software set up.
See also

* [Pi equipment](../escape pod/equipment.md) for information about the Raspberry Pi
  and charger that you will need
* [Pi issues](Pi issues.md) for information related to troubleshooting the Pi
  hardware
* [Pi connectivity](Pi connectivity.md) to troubleshoot the connection between your
  Pi, network and computer.  This includes Wifi, and mDNS troubleshooting.


## License code was not sent to Escape pod

Symptom:  After the hot-word, the wifi/no cloud animation will play.
There isn;t be a cycling white lights on the backpack.  This happens repeatedly.

This is indicates that the license code for this bot wasn't added to the Escape Pod.
(I know I've forgotten that once or twice.)

Follow the steps below to add a license.


## Unable to add the license

When going to the escape pod {the URL
[https://escapepod.local:8443/](https://escapepod.local:8443/)} you should see
a screen like:

![Add license](ep-add-license.png#zoom)
_Figure: You should see a blue add license button_

If you see the blue-tone Digital Dream Labs screen, but do not see the "Add
license to start" button there is a problem.  This is the button that you should see:

![Add license button](ep-add-license-button.png#center "Add license button")
_Figure: Add license button_

For instance, if you see swirling spinner -- it can be subtle -- like this:

![Swirling blue waiter](swirl-1.png#zoom "Swirling blue waiter")
_Figure: Swirling blue waiter_

this indicates a network naming issue.

Open the browsers error console.  Look for messages like the following:

```
    Failed to load resource: net::ERR_NAME_NOT_RESOLVED
    .local:8085/v1/license/add:1 Failed to load resource: net::ERR_NAME_NOT_RESOLVED
    DevTools failed to load SourceMap: Could not load content for https://escapepod:8443/react-router-dom.js.map: HTTP error: status code 404, net::ERR_HTTP_RESPONSE_CODE_FAILURE
```

If you have this problem, go to the following pages:

* [Computer setup](../escape pod/computer setup.md) for information about the
  software to install on your computer, and other adjustments to make mDNs work.
* [Pi connectivity](Pi connectivity.md#mDNS) to troubleshoot the mDNS
  configuration on your network and computer.


Alternatively, a person (me!) might have not noticed the swirly’s significance,
and clicked on "Add License".  That will bring up a screen, where one can enter
the license. After submitting, the page will appear unresponsive, then provide
an error like:


    ***** The entered license is not valid. Make sure you typed it in correctly and try again.**

These might occur if the url used "escapepod" or "escapepod.lan" or an IP
address to access the escapepod.  The "escapepod.local" name is not resolving
on the computer and it was hidden by the other names work.
If you have this problem, go to the following pages:

* [Computer setup](../escape pod/computer setup.md) for information about the
  software to install on your computer, and other adjustments to make mDNs work.
* [Pi connectivity](Pi connectivity.md#mDNS) to troubleshoot the mDNS
  configuration on your network and computer.

(In my case this was fixed by correcting 
the OpenWRT router’s default local domain.)

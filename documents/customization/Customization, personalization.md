# Customization
This is for notes on how to customize or personalize Vector.

See also: the [forums](https://forums.anki.com/t/what-have-you-found-so-far/43924)

It might be thru configuring the software and files:

- Sounds
- Body movements
- Eyes
- Colors?
- PNGs on face
- Backpack lights
- Cube lights
- Other custom animations

Or it might be physical changes, and tweaks that are distinctive and identify

.. Link to a showcase ..?


## Customizing animations

- animation  of eyes
- body movements
- boot animation


People would love tools to gen the animation file… but I suspect that may be hard.
The presentations made it sound like it was a lot of Maya rigging and plugins for
the export.. but since   Maya is expensive, and hard.. 

Maybe a Unity model tool could be made with a rigged model of Vector?
 and such for I suspect the value vs effort isn’t there for such a specialized area, but who knows?

Tools for generating animation files.

What about mixing-matching existing animations, and adjusting them slightly?

### Boot animation draft

Vector shows a boot animation at startup. This is located in /anki/data/assets/cozmo_resources/config/engine/animations/boot_anim.raw and it can be swapped out easily.

Digital Dream Labs has made a Python script which makes it easy to turn GIFs into animations very easily.

[DDL official instructions](https://oskr.ddl.io/doc/examples.html#change-boot-animation)

* A working installation of python with the Pillow package installed.

* An animated .gif with a resolution of 184x96 pixels

* The script gif_to_raw.py to convert the .gif to a raw image.

* Convert the .gif to a raw image:
`python gif_to_raw.py bootscreen.gif`
This will create a new file bootscreen.gif.raw

* Mount the filesystem for writing. Here we’ll do that from the host system:
`ssh root@192.168.1.110 "mount -o remount,rw /"`

* Use scp to copy the file in to place:
`scp bootscreen.gif.raw root@192.168.1.110:/anki/data/assets/cozmo_resources/config/engine/animations/boot_anim.raw`

* Reboot Vector from the host system:
`ssh root@192.168.1.110 "/sbin/reboot"`

## Sounds

## Behavior tree crafting

There are many json files in /anki/data/assets/cozmo_resources/config/engine/behaviorComponent/. Maybe have some examples of edits of those?



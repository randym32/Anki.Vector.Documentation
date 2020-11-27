# How to enable Cozmo-like animations for being on his side, and flipping down from being on his back

This is a note to describe how to enable (potentially) Cozmo-like animations
for being on  his side, and flipping down from being on his back.

Note: I don't know that these changes will make Vector more interesting

All of the files that we'll modify are in:
`/anki/data/assets/cozmo_resources/assets/animationGroups/ReactToCliff`

These animation group files change which animations are used to use more of
Cozmo's variety of animations.

Note: in general, not all animation groups that Cozmo uses are used by
Vector.  In this case, they are.


## Preparation

You’ll have to know how to SSH in, make the file system modifiable and edit a
file. To make the file system modifiable:

    mount -o rw,remount /

### Make backups of the animation group files

All of the files that we'll modify are in:
`/anki/data/assets/cozmo_resources/assets/animationGroups/ReactToCliff`

I recommend making a back up of the following files:

* ag_reacttocliff_stuckleftside_01.json
* ag_reacttocliff_stuckrightside_01.json
* ag_reacttocliff_turtleroll_01.json
* ag_reacttocliff_turtlerollfail_01.json

You can do this by copying it to a back up name.  For instance:

    cd /anki/data/assets/cozmo_resources/assets/animationGroups/ReactToCliff
    cp ag_reacttocliff_stuckleftside_01.json ag_reacttocliff_stuckleftside_01.bak
    cp ag_reacttocliff_stuckrightside_01.json ag_reacttocliff_stuckrightside_01.bak
    cp ag_reacttocliff_turtleroll_01.json ag_reacttocliff_turtleroll_01.bak
    cp ag_reacttocliff_turtlerollfail_01.json ag_reacttocliff_turtlerollfail_01.bak

If later on you want to go back to the orignal for any of these, you can reverse
this to restore it.  For example:

    cp ag_reacttocliff_stuckleftside_01.bak ag_reacttocliff_stuckleftside_01.json

## Make the files writeable

    chmod +x ag_reacttocliff_stuckleftside_01.json
    chmod +x ag_reacttocliff_stuckrightside_01.json
    chmod +x ag_reacttocliff_turtleroll_01.json
    chmod +x ag_reacttocliff_turtlerollfail_01.json

## Next Copy the replacement files 

Copy the replacement files to the that directory.
I've attached the files to this note, from Cozmo's APK.

You can copy them with `scp` or other method.
I use vi.

* ag_reacttocliff_stuckleftside_01.json
* ag_reacttocliff_stuckrightside_01.json
* ag_reacttocliff_turtleroll_01.json
* ag_reacttocliff_turtlerollfail_01.json


## Reboot 

Finally you have to restart the vic applications for the updates to load and take effect.
This can be done with:

    systemctl stop anki-robot.target
    systemctl start anki-robot.target

or a reboot.


## A few notes on possible next steps

You can edit a more animation group files and behaviors.
I tried to variations on

    ag_reacttocliff_wheelie_01.json

to make it Cozmo use the same animations that Cozmo calls out, but Vector would
no longer pop a wheelie for me.

Some of the animations files that these animation groups might not be fully
tuned for Vector and his cube's body.. and may need some further tweaking to
create the same energetic effect cozmo gives.

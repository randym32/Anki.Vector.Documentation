# Vector boards

## Head Boards

![Vector head-board top](vector head board top 1.jpg#zoom)
_Figure: Vector head-board top_

<! picture from Wire />

## Body boards

These drive the motors, talk with the time of flight sensor, pull the microphones sounds from the head board,
drive its LEDs, etc.

![Body Boaard top](vector body board top 1.jpg#zoom)
_Figure: Vector body-board top_

![Body Board bottm](vector body board bottom 1.jpg#zoom)
_Figure: Vector body-board bottom_

Some initial body-board [wiring schematics](Vector Body Board Schematic.pdf) 
(rather than function-focused) and
Feel free to edit the [EasyEDA](Vector Body Board Schematic.json) file.


### Body Board Firmware

Each revision of the body board has a bootloader specific to that revision;
the boot loaders holds a revision code at 0x08000010.  (In some cases, this
revision code may be the only change.)  This revision code
(or number) is used by the application firmware (held in syscon.dfu) to know
which board it is running on, and make small changes to accomodate the differences.

| Body-Board Type | Revision Code | Description and Notes |
|-----------------|---------------|-----------------------|
| DVT1            | 1             | |
| DVT2            | 2             | |
| DVT3            | 3             | |
| DVT4            | 4             | This board has significant changes from the DVT3.  DVT4 also corrected a regulator problem (although that may be on the headboard.) |
| PVT             | 5             | |
| Production      | 6             | The LED clock and data lines have moved, adding a line to manage power for the head or backpack. |
| Whiskey         | 7             | Version 1.4 of the syscon does not work correctly with this board; this suggests that the Whiskey body board was manufactured after the 1.4 firmware was made.|

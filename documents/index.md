# Vector Resources

This is a wiki for gathering and sharing information about
[Anki Vector](https://www.anki.com/en-us/vector) 

## Personalizing Vector
This is for notes on how to customize or personalize Vector.
You may have to consult the How-To's below.

See also: the [forums](https://forums.anki.com/t/what-have-you-found-so-far/43924)

## Troubleshooting
- [What Do Vector's Back Lights Mean?](troubleshooting/Backpack lights.md)
- How to check for software problems
- The big long list of error codes is Appendix D of the [Technical Reference Manual](https://github.com/GooeyChickenman/victor/raw/master/documentation/Vector-TRM.pdf), and in TBD

See also the [troubleshooting at DDL's site](https://support.digitaldreamlabs.com/category/16-troubleshooting):

* Troubleshooting Vector's Connection
* How Do I Find Vector's Serial Number?
* Why does Vector need a 2.4 GHz network?
* Vector does not understand me: Troubleshooting Speech Recognition
* What Do Vector's Back Lights Mean?
* Why does Vector show an error?
* Troubleshooting charging issues
* Why is there no sound?


## Service Guide
Collected notes on repairing or modifying Vector.

- Assembly and [exploded view diagrams](service/Exploded View.md).  I am a sucker for exploded diagrams and drawings.
- How to update software
- How to clean wheels/sensors
- Where to [get parts](service/Parts kits.md) -- treads, etc.
- How to replace the battery?
- Boards?


## How-Tos
These try to tell you how to accomplish particular tasks.

Some highlights:

* Using GDB [to trace function calls](how-to/GDB tracing.md)
* Using AudioKinetic WWise to [convert sound files to WEM format](how-to/Using AudioKinetic WWise to convert sound files to WEM.md)

* Dauler sells stickers with the marker symbols prepirnt at (3D Designs by Dauler)[https://designsbydauler.com/collections/vector-robot]

## Developer documentation
These are reference documentation for programming tools to use Vector.
Some of them are for the remote-access SDK's.

### [Technical Reference Manual](https://github.com/GooeyChickenman/victor/raw/master/documentation/Vector-TRM.pdf)
* Details on how Vector _works_
* Main architecture of the design (not necessarily the code though) and how it works
* File system structure, files, formats and contents
* Communication protocols

### Programmers Guides and Examples
PC/Mobile SDK (HTTPS API)

- Python Communication SDK: [Vector - Python SDK](https://github.com/ikkez/vector-python-sdk)
- C# Communication SDK: [Anki.Vector.SDK](https://github.com/codaris/Anki.Vector.SDK)
- C# [Anki.Resources.SDK](https://github.com/randym32/Anki.Resources.SDK)

- See the SDK examples

Bluetooth LE implementations.  There isnt an SDK for the Bluetooth LE protocol,
but there are a few implementations that you might wish to look at/reuse:

- [OS-X Objective-C](https://github.com/GooeyChickenman/victor/tree/master/tools/vector-BLE)
- [linux & C](https://github.com/sandsmark/victor/tree/master/tools/vector-BLE)
- [Chrome & Javascript](https://github.com/kercre123/victor-web-setup) and [here](https://github.com/digital-dream-labs/vector-web-setup)

### WebViz and Console Variables
The developer builds of Vector's softw w

### Application Notes
TODO

### [Vector Enhancement Proposals](vector-enhancement-proposals/Overview.md)
These are proposals for changes -- enhancements -- to the modules on Vector.

Some highlights:

* An [overview](vector-enhancement-proposals/Overview.md) of the overall proposal process.
* VEP1. [Update-engine changes](vector-enhancement-proposals/VEP1 - Update-engine changes.md)
* VEP2. [Packagement for modules on Vector](vector-enhancement-proposals/VEP2 - Package management for modules on Vector.md)


## Historical Bots
This might a place for odds and ends info 

- DVT bot info
- Whisky info
- etc


## Stuff to help collaborate

### Guidance

These provide tips/suggestions on style, naming.
They are related to the "How-to's" but they don't walk you thru to a specific goal.
For instance, some might describe how to a do a particular style of design or implement a kind of behavior.


Examples:

 - Recommendations for sound event names
 - Steps that a design/process can do to meet the spec

Good title:

Bad title:

Writing guide.

- Other writer guides
- Show how to do something in general, like a tutorial
- Document and show off how you built one of your projects
Background: This is a note I made for myself to guide me on the right tone, help with consistency and give me some direction.

### Templates
The document-templates folder includes some start files that can be used as templates
when creating new documents:

* A template for [how to documents](document-templates/how-to.md)
* A [generic template](document-templates/template.md) for other files

# Vector Resources

This is a wiki for gathering and sharing information about
[Anki Vector](https://www.anki.com/en-us/vector) 

[PDF version](./Vector-Wiki.pdf)

See also this other [Wiki by Xanathon](https://wiki.thedroidyouarelookingfor.info/doku.php?id=start)

## Games and Things you can do with Vector

* A ["cheat sheet" of the things you can say to Vector](https://cheatography.com/tme520/cheat-sheets/anki-vector/) by Samuel Ward.  ([pdf](https://cheatography.com/samuelward/cheat-sheets/anki-vector/pdf/))
* Another [Vector command list](https://github.com/lukemerrett/Anki-Vector-Command-List)
* [A Guide to the Vectorverse](https://docs.google.com/document/d/e/2PACX-1vSssbqqD_CS1Ib99EcXs3qEB-AXHhpxNGNpI1-I7Avfd0Jtgzq1n88aYGFakNzWRnnhZdlediRN9Uly/pub)
   by Stephan Otter (@StephanOtter) and Steven Coblentz (@SteveCoblentz).  This
   is a document on the interactions and games you can play with Vector.

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
* How to [create a soundbank](how-to/How to create a soundbank.md)
* Dauler sells stickers with the marker symbols preprinted at
  [3D Designs by Dauler](https://designsbydauler.com/collections/vector-robot)

## Developer documentation
These are reference documentation for programming tools to use Vector.
Some of them are for the remote-access SDK's.


<a name="TRM"></a>
### [Technical Reference Manual](https://github.com/GooeyChickenman/victor/raw/master/documentation/Vector-TRM.pdf)

* Details on how Vector _works_
* Main architecture of the design (not necessarily the code though) and how it works
* File system structure, files, formats and contents
* Communication protocols

### Programmers Guides and Examples

The main PC/Mobile SDKs are:

- Python Communication SDK: [Vector - Python SDK](https://github.com/ikkez/vector-python-sdk)
- C# Communication SDK: [Anki.Vector.SDK](https://github.com/codaris/Anki.Vector.SDK)

- See the examples with each of the packages

See the [SDKs page](software-design/SDKs.md) for more repositories and other resources.

### WebViz and Console Variables
"Pure" Developer builds of Vector software contain an HTTP API and webserver. This shows what it is, how to use it, and how it works.

### The Communication Protocols

The communication protocols Vector uses to talk to the cloud.
(Several of the protocols were specified with gRPC and Protobuf.  The information
here was reconstructed from binaries, WebViz, logs and other sources.  It is
hoped to allow reconstruction of significant portions of the Protobuf specification.
If the source protobuf specification files do become available later, these can be
used to comment them.)

### [Vector Enhancement Proposals](vector-enhancement-proposals/Overview.md)
These are proposals for changes -- enhancements -- to the modules on Vector.

Some highlights:

* An [overview](vector-enhancement-proposals/Overview.md) of the overall proposal process.
* VEP1. [Update-engine changes](vector-enhancement-proposals/VEP1 - Update-engine changes.md)
* VEP2. [Packagement for modules on Vector](vector-enhancement-proposals/VEP2 - Package management for modules on Vector.md)


## Historical Bots
This is a place for info about robots that were part of Vector's evolution, but are products in their own right.

- DVT1-4 bot info
- Whiskey info
- Bingo info
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
To help get started with creating a new entry, the document-templates folder
includes some start files that can be used as templates when creating new
documents:

* A template for [how to documents](document-templates/how-to.md)
* A [generic template](document-templates/template.md) for other files

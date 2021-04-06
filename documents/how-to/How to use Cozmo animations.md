# How to use Cozmo animation files

Cozmo's animation .bin files can be used on Vector, mostly.  You do need know how to trigger them.

## Why does this even work?

Cozmo's animation schema is very similar to Vector’s.  
When Vector reads and interprets the animation file it uses the flatbuffers library.  This library uses default values for fields that are missing in a file — fields that Vector uses but that the Cozmo animation files doesn’t provide.  And the library ignores fields in the file that it doesn't know about — fields that Cozmo uses but Vector doesn’t.  So that gives it a lot of compatibility for faces, lights, motions.

Where Vector completely ignores Cozmo features is the sound.  The sound features in the animation files is completely different between the two.  (If cozmos sounds tracks work without fuss, Id be surprised ... or maybe they have a Cozmo compatibility layer?)


## How to get a Cozmo animation file

## How to put it on Vector

- Include how to link it into the behavior or what not

## What about fixing up the audio stuff?

A bit of background the animation files send audio events, or audio trigger names (plus some audio parameter adjustments) that are used to tell the audio engine to play a particular sound.

You will have to convert the animation to JSON  Then edit them to the new schema and change the audio trigger name to one that Vector supports.  Then repack it into an animation bin file.

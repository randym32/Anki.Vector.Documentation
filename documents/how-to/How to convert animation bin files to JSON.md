# How to convert animation bin files to JSON


The animation binary files are based on Google's flatbuffers using a binary format.  Forturnately it is easy to read,
since Anki left the description file in the Vector software, and it is an evolution of what was used in Cozmo.  

The files can be turned into JSON, and then back.  Google's tools will do this for you, see 
["Using flatc as a JSON Conversion Tool"](https://google.github.io/flatbuffers/flatbuffers_guide_tutorial.html)

You can also turn the JSON file back into a binary file using the same tool.

## Developer Animation JSON files

The developer releases of Vector software includes animation JSON files.  These are the equivalent to animation binaries, but in JSON format.
The developer software -- and perhaps the production software as well -- can read the animation in the JSON form.



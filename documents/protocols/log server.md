# Log Server for Vector
This is an overview of how a server to receive logs from Vector can work.

## The file system layout
I created a folder to store information from this Vector's logs.  The
received file contents in the HTTP upload will be saved in a folder nested
underneath that.  This is the naming scheme that I settled on:

    [Server base] / [serial #] / year-month /  [ time stamp] 

This creates separate directory trees for each robot, even if the name
robot name changes.

Next is a folder for each month.  The format I went with has year as a 4 digits, and months as two digits in my example.  (yyyy-MM). 

Finally each upload gets its own timestamped folder — timestamped with the
time it was received.    I used the format.  The contents differ with each
kind of upload.

_Why is there a separate folder for each month?_
Vector produces at least 50-100 DAS files per day;  This can create a lot
of files (and folders) very quickly.  If we don't spread them across a few
sub-folders, the number of files for a given folder is too much for a
person to manage.  Then, at a bit larger number, the OS will have a
collapse in efficiency, taking exponential time to list or access the
files.  The number depends on the file system and OS... it could be 32768,
or 65536 or less.   In other words, a single robot could create 36500
uploads in a single year, that is too much people and computers in a single
folder, so I had ‘em spread out.

## The types of data sent in logs
The types of data and file formats:

- The crash logs 
- minidump
- DAS json events
- Linux system logs.  Note: as I recall these might be included in the
  crash logs.  Thee SDK can also trigger sending them

Things not included:

- Wifi info: understanding the issues the network connectivity: data rate,
  latency, dropped connections.  This might be part of the logs sent above
  ( I don't recall) but aren't separately gathered and sent.

## How to decide what kind of file has been received.

1. Look at the file name (excluding the path) of the posted file.  If the file name is "DAS" (regardless of case), and this is a HTTP POST (not a form), it is DAS log upload; otherwise
2. Look at the name of the file without the extension and drop the file extensions.  If the file name starts with “victor-“ (regardless of case), this is a compress Vector log file archive.
3. Check for the HTTP header,"Usr-RobotESN" If there is one, this is a fault report containing crash dumps… Otherwise,
4. Does it have a body?  Then it is a crash dump

### DAS files
The DAS upload includes the data in the HTTP stream content.  The serial number for the robot is buried in the DAS contents, so has to be extracted /after/ the stream has been received.

* Looked for the attached “MessageBody.json.gz” that is the DAS events to save to the folder.  Decompress a copy, read the first record and pop the robot id for the folder to save it in.
* Save the parameters associated with the stream to a file called "params.txt"
* Save the header fields to a file called “info.txt” in the folder.  The most important are:
UserAgent
RemoteEndPoint

### The log files 
This stores the logs uploaded from the Vector
The robot's electronic serial number is the part after the "victor-" in the file name.
When logs files are uploaded, I found it was important to store some meta related to the upload.  I saved the header fields to a file called "info.txt" in the folder.  The most important are:

* _UserAgent_
* _RemoteEndPoint_

This includes a file attached to the upload.  This uploaded file is saved to the folder.

### Crash Dumps
The crash dumps are multiple parts attached to a form upload stream. 
The robot serial number is in the form parameter "robot.esn".
If there isn’t one associated, fall back to "unknown"
I saved the header fields to a file called "info.txt" in the folder.  The most important are:


* _UserAgent_
* _RemoteEndPoint_

The form parameters fields are captured into a file called "params.txt"
The files attached to form are also saved to the folder (using the name of the file, not any other parts of the path.)

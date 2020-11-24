# How change where Vector sends the logs

This is a note describing how to change where your Vector sends logs.
You will need a program on your computer to receive the logs.

Vector sends the following kinds of logging information to remote servers:

- DAS Events
- Log upates, when triggered by the SDK
- Crash logs
- Crash minidumps

This is the files to change to send the logs (etc) to your own server:

For the purposes of this writeup, lets assume that your server is located
at the following address:

``http://192.168.1.224:8888/``

This is also getting packaged up in a [vpkg file](TBD.md) but you will have to make changes on your own

## Modifying the configuration file(s)

The config file that we need to modify is:

``/anki/data/assets/cozmo_resources/config/DASConfig.json``

It probably looks like:

```json
{
  "dasConfig" : {
    "url": "https://sqs.us-west-2.amazonaws.com/792379844846/DasInternal-dasinternalSqs-1HN6JX3NZPGNT",
    "file_threshold_size": 100000,
    "flush_interval": 600,
    "storage_path": "/run/dasLogs",
    "storage_quota": 5000000,
    "backup_path": "/data/data/com.anki.victor/cache/dasLogs",
    "backup_quota": 10000000,
    "persistent_globals_path": "/data/data/com.anki.victor/persistent/dasGlobals.json",
    "transient_globals_path": "/run/dasGlobals.json"
  }
}
```

We need to change the "url" line use our local URL.
From:

``    "url": "https://sqs.us-west-2.amazonaws.com/792379844846/DasInternal-dasinternalSqs-1HN6JX3NZPGNT",``

to

``    "url": "http://192.168.1.224:8888/das",``


So the configuration file will look like:

```json
{
  "dasConfig" : {
    "url": "http://192.168.1.224:8888/das",
    "file_threshold_size": 100000,
    "flush_interval": 600,
    "storage_path": "/run/dasLogs",
    "storage_quota": 5000000,
    "backup_path": "/data/data/com.anki.victor/cache/dasLogs",
    "backup_quota": 10000000,
    "persistent_globals_path": "/data/data/com.anki.victor/persistent/dasGlobals.json",
    "transient_globals_path": "/run/dasGlobals.json"
  }
}
```


There is a second configuration that is tempting to modify.  We won't need to.
But lets look at it any way.  The file path is:

``/anki/data/assets/cozmo_resources/config/server_config.json``

It has the following contents:

```json

{
        "jdocs": "jdocs.api.anki.com:443",
        "tms": "token.api.anki.com:443",
        "chipper": "chipper.api.anki.com:443",
        "check": "conncheck.global.anki-services.com/ok",
        "logfiles": "s3://anki-device-logs-prod/victor",
        "appkey": "oDoa0quieSeir6goowai7f",
        "devappkey": "xiepae8Ach2eequiphee4U",
        "offboard_vision": "192.168.1.224:8888"
}
```

It looks tempting to change "logfiles" entry.
We're going to bypass it completely.


## Now add more scripts

Download the [rcm-log-upload](rcm-log-upload) script and place it in the
'/anki/bin/' directory on your Vector.

(We can improve the name later)

Edit this file.  (We could use your help to use a proper .env file for
configuration here)  Look for the line:

``: ${VIC_LOG_URL:="http://192.168.1.224:8888"}``

Change the IP address and port number to the one your server uses.

### Editing vic-log-uploader

Next step is to edit  `/anki/bin/vic-log-uploader` so that it will use the
modified uploader.

Change the line

```UPLOADER="/anki/bin/vic-log-upload"```

to

```UPLOADER="/anki/bin/rcm-log-upload"```

### Editing vic-crashuploader.env

Now edit `/anki/etc/vic-crashuploader.env` so that the crash dump script will
send the minidumps to your server.

Look for the line that starts with `VIC_CRASH_UPLOAD_URL`

``VIC_CRASH_UPLOAD_URL='https://anki.sp.backtrace.io:6098/post?format=minidump&token=6fd2bd053e8dd542ee97c05903b1ea068f090d37c7f6bbfa873c5f3b9c40b1d9'``


And change that to your local server.  For instance:

``VIC_CRASH_UPLOAD_URL='http://192.168.1.224:8888/'``


## What about the server on my computer ?

We need help creating a python or node.js program to receive the variety of log
and crash files.  Contact Randy (randym@randym.name) if you can help, or for a
reference C# program that works on Windows.... (it does require granting a lot
of permissions tho')

## Finally reboot, if you want

Vector won't use the new server addresses (in most cases) until you do a
reboot

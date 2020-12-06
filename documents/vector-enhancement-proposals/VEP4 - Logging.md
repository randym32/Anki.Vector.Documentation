---
title: VEP4 - Logging
summary: Changes to the logging scripts, configuration to local servers.  This is to modify the servers to use for the logging, crash dumps, and similar.  Events/logs will no longer be sent to AWS, or backtrace.io.
authors: Randall Maas
---

This a draft proposal (to be filled in) on how to modify Vector config files and scripts to send logging and crash
dumps to a server of our choosing.

- Logging
- Trace information
- Server
- Settings
- DAS optin/optout

Replace `/anki/bin/vic-log-upload`

- moving aside, `/anki/bin/vic-log-upload` since it just does AWS, S3://
- put in something that can contact our local server

Files:

* server_config.json
* log uploader
 
## References

See [How change where Vector sends the logs](How to change where the logs are sent.md)
for example changes to the configuration files.

## Change history synopsis

|Date|Change|
|----|------|
|2020-11-17|Created|

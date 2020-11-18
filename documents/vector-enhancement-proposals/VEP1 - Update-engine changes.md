---
title: VEP1 - Update-engine changes
summary: Update-engine changes to make for unsigned, incremental updates; and to reduce the number of partitions modified.
authors: Randall Maas
---


## Description of the changes
Motivation: Building a new, experimental development release is not possible with an stock update-engine:

1. We can't create an OTA file for unmodified production, development and OSKR bots, as it needs to be signed in order for the update-engine to apply it.

2. The OTA update is very "heavy weight" -- it needs to update the boot and system files systems (with a
200+MB file!) just to change a couple of files.

This enhancement changes the following to the update engine:

- remove signing check of the manifest, update files
- Allows replacing individual partitions, esp just the system file system; usually it replaces several at a time
- Allows using tar to update the contents of the system file system
  + This is not recommended since it doesn't get the permissions right


## Documentation
 - none at this time

## Cavaets
 - the tar based updating of the system file system doesn't always work as expected, since the busybox tar doesn't preserve permissions
 - it is tricky to create a tar file
 - there is no undo for a partial update
 - this probably doesn't disable delta updates properly, so if a delta update were to be issued, we'd need a way to make sure it doesn't mess up the FS.

## Status
 - it works well (except the system fs file-only changes), I believe that Wire has used this or a modified version
 - I am considering other changes to support package-based updates to the file system, to better address the above issues.
 
## References
## Change history synopsis



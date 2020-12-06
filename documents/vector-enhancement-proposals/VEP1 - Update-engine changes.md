---
title: VEP1 - Update-engine changes
summary: Update-engine changes to make for unsigned, incremental updates; and
         to reduce the number of partitions modified.
authors: Randall Maas
---


## Description of the changes
Motivation: Building a new, experimental development release is possible but
inconvenient with an stock update-engine:

1. The OTA update is very "heavy weight" -- it needs to update the boot and
   system file-system partitions (with a 200+MB file!) just to change a couple
   of files.

2. Creating an update an OTA file for OSKR bots and modified development bots
   is possible, but it too difficult for most people. 

3. There is no way to blend changes from updates.

This enhancement changes the following to the update engine:

- Making the signing check of the manifest, update files optional
- Making the encryption of the OTA optional
- Allows replacing individual partitions, esp just the system file system
- Allows using a package manager or other tool to update the contents of the
  file system.
    + A package manager has been created to help with the process, and handle
      issues like file permissions.  See
      [VEP2 - Package management for modules on Vector](VEP2 - Package management for modules on Vector.md)

## Some Design decisions

Using the `tar` utility is not used, and we found a small tool modify for out
purposes instead.  The busybox `tar` doesn't preserve permissions, which led
to unexpected results and problems when updating executables.


## Documentation

The `update-engine` looks the same to the rest of the system as before.
(The OTA format, rules are described in the TRM...)
It now accepts URLs with a `.vpkg` extension.  If these are seen, the 
There is no at this time.  

## Cavaets

- this probably doesn't disable delta updates properly, so if a delta update
  were to be issued, we'd need a way to make sure it doesn't mess up the FS.

## Status
The update

 - I believe that Wire has used an earlier modified version
 
## References

* The format and rules of the OTA files are in Chapter 32 of the
  [Technical Reference Manual](https://github.com/GooeyChickenman/victor/raw/master/documentation/Vector-TRM.pdf)

* A reference implementation of these changes is on github in a [gist](https://gist.github.com/randym32/67cad96725c765e5398334f2cba5ac2f)


## Change history synopsis

|Date|Change|
|----|------|
|2020-8-30|Created|
|2020-12-6|Updated formatting, updated based on changes to 1.7.1, links to code style.   Note: Changes in 1.7.1 made it  possible to create -- especially encrypt and sign -- the files, a feature needed by the update-engine.  Earlier versions of this proposal were mandated because of the inability to sign.|


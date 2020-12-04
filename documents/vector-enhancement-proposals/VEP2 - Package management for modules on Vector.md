---
title: VEP2 - Package management for modules on Vector
summary: Supports installing and uninstalling packages/modules on Vector
authors: Randall Maas
---

Note: this isn't modules for source code.

## Description of the changes
Motivation: We needed a way to package changes to a few files on an already
deployed system, to ensure that the permissions are correct on the files
(usually executable), and some restrictions/protections from screwing up system
files.  (Ie, don't force it to be unbootable)

This is a package manager that does those, and adds in a few extras:

- It allows modifying parts of a file, usually the version identifier of the
  system, so we know what we're working with.
  
- Lists the installed packages

- Can uninstall packages

- Can set the premissions for the files.

## Some Design decisions:
- The tool had to be small, and not hard to deploy

- The tool can’t be compiled (we don't know how)

- It had to be based on tools already on Vector: python 2.7, and busybox based
  utils.  Busybox supplies the shell, and tar... except tar doesn't support
  preserving permissions.

- It is preferred to separate out the package manager from the update-engine
  as much as possible, to make int more understandable and support testing.


### It just installs the packages
This tool doesn't do everything that the other managers do:

- It doesn't check dependencies
- It doesn't download files
- It has minimal the pre-flight, post-flight scripts that are run.

The package download is handled by either the update-engine (and its line of
control), or by scp command.  The lack of dependency check is a benefit, as its
hard to maintain, and it is rarely used correctly: maintainers tend to choose a
dependency of "the latest version" (as of when the package was), negating its
use.

## Documentation
The documentation of the tool is included as part of it's tgz. This is a
quick overview.

When a package is installed it creates another package taking a snapshot of
those files already there.  When the package is uninstalled this 2nd package
is used to replace the newer files with the older ones.  It doesn’t delete any
files that were added since or by the first package, so some extra stuff can
accumulate, but that is far safer.

Creating a package.  To create a package, lets call it demo, requires setting
up the files sytem with the files, and the package manifest.  The manifest
says, among other things:

 1. The package name, version, and other helpful paperwork info.
 2. where to get the files from locally, and where they should be placed into
    filesystem deployed when deployed on a Vector.
 3. The path to any files that should be modifed, and how.  This is used to
    change the reported version string.
 4. The permissions to set the files to

I've attached a really simple demo to demonstrate.  To create a package unzip
them, and then:

```bash
   ./vector-pkg.py create —pkg=demo
```

That will create .vpkg file — a gzip'd tar file with a specific layout.  From
here everything has to be on a Vector.

Installation.  To install the vpkg:

```bash
   ./vector-pkg.py install —pkg=demo-1.vpkg
```

Uninstall.  To uninstall the vpkg later

```bash
   ./vector-pkg.py uninstall —pkg=demo-1
```

### Adding a restart step after installation

There are four different ways to restart after applying the package.
To simply restart Vector's application:

    [post_deploy]
    0=systemctl stop anki-robot.target
    1=sleep
    2=systemctl start anki-robot.target

To restart Vector's application, but silently -- that is, not play the
*InitialWakeUp* animation:

    [post_deploy]
    0=systemctl stop anki-robot.target
    1=sleep
    2=echo 1 > /data/maintenance_reboot
    3=systemctl start anki-robot.target


If `vector-pkg` is by called the modified `update-engine` it can tell it to
reboot the operating system after the package has installed, using the key
`reboot_after_install` in the `META` section.  For example:

    [META]
    reboot_after_install=1

The following will reboot the operating system using a "maintenance reboot"
so that the *InitialWakeUp* animation is not played:

    [post_deploy]
    0=/anki/bin/vic-log-event update-engine robot.maintenance_reboot success
    1=echo 1 > /data/maintenance_reboot

## Cavaets



## Status
Not tested by others yet.
Once the bugs are shaken out, the update-engine can be tweaked.  When the
update-engine gets a URL with ".vpkg" (such as from the BLE app) at the 
end, it downloads it, and then pass it to the package manager.

## References

The files are on github [https://github.com/randym32/Anki.Vector.PackageInstaller](https://github.com/randym32/Anki.Vector.PackageInstaller)

## Change history synopsis


|Date|Change|
|----|------|
|2020-8-30|Created|
|2020-12-3|Added how to restart after installing a package|

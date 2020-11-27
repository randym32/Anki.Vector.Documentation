# How to set up a new Yocto-linux build environment for Vector’s base OS 

This is how to create a new build environment for Vector's base OS -- Yocto Linux and his drivers.
_Note: this does not include the Vector application software!_

Steps.

1. Install Ubuntu (or reuse a machine with Ubuntu) 
2. Get Yocto installed, e.g. using Docker
3. Install the base OS source code
4. Test build

## Install Ubuntu

Your options are:

1. You already use Ubuntu, so you don’t need this (skip to the next section)
2. You want to install it on a VirtualBox on your computer:

    * Follow the instructions here to set up the basics (this sets up Ubuntu
      16.04 but you can use others) https://medium.com/@tushar0618/install-ubuntu-16-04-lts-on-virtual-box-desktop-version-30dc6f1958d0
    * Double the size of the harddrive though!
    * As part of this you will need the "ISO" file for the Ubuntu OS.  Select
      your particular version of Ubuntu and download the ISO from here:
      [Ubuntu 16.04 download](https://releases.ubuntu.com/16.04/)  (This is 16.04,
      switch to version that matches your preference)

3. You want to install it on your Raspberry Pi or on something else.  (You’ll have to let us know what those instructions are!)

# Install Docker image
We'll  use a docker image (vaddio/yocto-16.04) to preinstall Yocto dependencies.

1. First start a command shell.  This done by clicking on the Ubuntu logo at the top left, typing "command line" and selecting the terminal application.
2. Next, install docker.
```
    sudo apt install docker.io
```
3. Install vaddio/yocto-16.0.04
```
    sudo docker run -it vaddio/yocto-16.04:16.04-latest /bin/bash
```

## Install the base OS source code
Now that Docker and Yocto are installed, we need to install the source code specific for Vector:
```shell
    sudo chmod 0777 .  && sudo su builduser
    curl https://anki-vic-pubfiles.anki.com/license/prod/1.0.0/licences/OStarball.v160.tgz | tar -xz
```

## Perform a test build
Finally, it's time to perform a test build.  This will run a **long** time:
```
    cd opensource/poky && source build/conf/set_bb_env.sh && build-victor-robot-image
```

To remove the intermediate files then:
```
    buildclean
```

The && are used to avoid multiple run commands.  Each run "command creates a new container with the deltas."

## Credits:
Information from [nammo on discord](https://discord.com/channels/527874754342944770/683843979908874397/771738630955728936)


# How to unzip the OTA files

See the [Project Victor Firmware folder](https://github.com/GooeyChickenman/victor/tree/master/firmware)
for a description how to download the .ota files and how to verify them.  It
also includes a tool that can aid with the extraction.

There are three parts

1. First, the OTA's have to be decrypted
2. Next, the system files are extracted from the sysfs archive
3. Finally boot initramfs files can be extracted.  (Their archive is a bit different)

## Decrypting the OTA archives

The OTA files are tar.gz files, so they can be opened with tar (or similar tool).  Among the files inside are two files:

`   apq8009-robot-boot.img.gz` (encrypted)

`   apq8009-robot-sysfs.img.gz` (encrypted)

Decrypting these files is done by:

`openssl enc -d -aes-256-ctr -pass file:ota.pas -in apq8009-robot-boot.img.gz -out apq8009-robot-boot.img.dec.gz`

`openssl enc -d -aes-256-ctr -pass file:ota.pas -in apq8009-robot-sysfs.img.gz -out apq8009-robot-sysfs.img.dec.gz`


With OpenSSL 1.1.0 or later, add “-md md5” to the command:

`openssl enc -d -aes-256-ctr -pass file:ota.pas -md md5 -in apq8009-robot-boot.img.gz -out apq8009-robot-boot.img.dec.gz`

`openssl enc -d -aes-256-ctr -pass file:ota.pas -md md5 -in apq8009-robot-sysfs.img.gz -out apq8009-robot-sysfs.img.dec.gz`

The keys can be found in the [detail/keys folder](https://github.com/GooeyChickenman/victor/tree/master/detail/keys) in the Project Victor repository.

## Unziping the system filesystem (sysfs) archive

On windows, the decoded `.img` files can extracted with 7zip

On linux, you can mount the file

1. gunzip the decrypted `apq8009-robot-sys.img.dec.gz`
2. `sudo mkdir /media/iso`
3. `sudo mount -o loop apq8009-robot-sys.img.dec /media/iso`

## Unziping the boot initramfs filesystem (boot) archive

There are a couple of alterantives for tool sets:

* With Linux and Windows 10, there is a convenient tool 
* For other systems, imgtool/imjtool from the New Android Book works


### Linux and Windows 10 WSL methd

1. Go to 
[How to unpack and repack boot and ramdisk files easily](https://nerdschalk.com/how-to-unpack-and-repack-boot-and-ramdisk-files-easily/) 
and follow the directions for the tool down load and installation

2. Added them to my path,
3. Opened wsl
4. gunzip the decrypted `apq8009-robot-boot.img.dec.gz`
5. Finally "unpack apq8009-robot-boot.img" 


### imgtool / imjtool  

For other systems there is a help tool already exists

1. Download, build and install [imjtool](http://newandroidbook.com/tools/imjtool.html)
2. gunzip the decrypted `apq8009-robot-boot.img.dec.gz`
3. Extracted the files using the image tool

```  imjtool boot.dec.img extract```

That creates an extract folder with the ramdisk.  The ramdisk is in "cpio"
format.

Finally Extracted the files with

  cd extract
  gzcat ramdisk| cpio -idmv


## References and Resources

The decryption was originally posted to the [Anki Vector Rooting google group](from https://groups.google.com/forum/#!searchin/anki-vector-rooting/openssl%7Csort:date/anki-vector-rooting/YlYQsX08OD4/fvkAOZ91CgAJ) 

[How to unpack and repack boot and ramdisk files easily](https://nerdschalk.com/how-to-unpack-and-repack-boot-and-ramdisk-files-easily/) on Linux and windows 10

* imgtool — now called [imjtool](http://newandroidbook.com/tools/imjtool.html)

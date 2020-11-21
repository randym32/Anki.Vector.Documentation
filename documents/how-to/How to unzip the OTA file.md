See the [Project Victor Firmware folder](https://github.com/GooeyChickenman/victor/tree/master/firmware) for a description how to download the .ota files and how to verify them.  It also includes a tool to perform the extraction.

The OTA files are tar.gz files, so they can be opened with tar (or similar tool).  Among the files inside are two files:

`   apq8009-robot-boot.img.gz` (encrypted)

`   apq8009-robot-sysfs.img.gz` (encrypted)

Decrypting these files is done by:

`openssl enc -d -aes-256-ctr -pass file:ota.pas -in apq8009-robot-boot.img.gz -out apq8009-robot-boot.img.dec.gz`

`openssl enc -d -aes-256-ctr -pass file:ota.pas -in apq8009-robot-sysfs.img.gz -out apq8009-robot-sysfs.img.dec.gz`


To use OpenSSL 1.1.0 or later, add “-md md5” to the command:

`openssl enc -d -aes-256-ctr -pass file:ota.pas -md md5 -in apq8009-robot-boot.img.gz -out apq8009-robot-boot.img.dec.gz`

`openssl enc -d -aes-256-ctr -pass file:ota.pas -md md5 -in apq8009-robot-sysfs.img.gz -out apq8009-robot-sysfs.img.dec.gz`

The keys can be found in the [detail/keys folder](https://github.com/GooeyChickenman/victor/tree/master/detail/keys) in the Project Victor repository.

(from https://groups.google.com/forum/#!searchin/anki-vector-rooting/openssl%7Csort:date/anki-vector-rooting/YlYQsX08OD4/fvkAOZ91CgAJ) 

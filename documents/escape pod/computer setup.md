# EscapePod: Computer setup 

## On Your Computer

You should have Chrome Installed.


## Windows Computers

If you have a Windows computer, you need some software installed for “mdns”.  If you have iTunes installed, this software is already installed for you and you can skip this step.  If not, install bonjour from:

* [https://support.apple.com/downloads/bonjour_for_windows](https://support.apple.com/downloads/bonjour_for_windows)

Then, on the command line


    REG ADD  “HKLM\Software\policies\Microsoft\Windows NT\DNSClient”

    REG ADD  “HKLM\Software\policies\Microsoft\Windows NT\DNSClient” /v ” EnableMulticast” /t REG_DWORD /d “0” /f



## Replacement for the Mobile App

The mobile application will not work.  It expects to talk with the production servers and doesn’t know how to work with the EscapePod.  Instead, use Vector Explorer by Wayne Venables at:

* [https://weekendrobot.com/vectorexplorer/](https://weekendrobot.com/vectorexplorer/)

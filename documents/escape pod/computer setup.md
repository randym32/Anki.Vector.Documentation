# Computer setup 

## On Your Computer

You should have Chrome Installed.


### Windows Computers

If you have a Windows computer, you need some software installed for "mdns".
If you have iTunes installed, this software is already installed for you and
you can skip this step.  If not, install bonjour from:

* [https://support.apple.com/downloads/bonjour_for_windows](https://support.apple.com/downloads/bonjour_for_windows)

Then, on the command line


    REG ADD  “HKLM\Software\policies\Microsoft\Windows NT\DNSClient”

    REG ADD  “HKLM\Software\policies\Microsoft\Windows NT\DNSClient” /v ” EnableMulticast” /t REG_DWORD /d “0” /f


### Linux

If you have a Linux computer, you may need to make a make change
to the '/etc/nsswitch.conf'.
_Note: this section is not yet confirmed_

In a command line, open the  'etc/nsswitch.conf' file.  It probably will look
like this:

<pre>
    #
    # Example configuration of GNU Name Service Switch functionality.
    # If you have the `glibc-doc-reference' and `info' packages installed, try:
    # `info libc "Name Service Switch"' for information about this file.
    passwd:         files systemd
    group:          files systemd
    shadow:         files
    gshadow:        files
    <b>hosts:          files mdns4_minimal [NOTFOUND=return] dns</b>
    networks:       files
    protocols:      db files
    services:       db files
    ethers:         db files
    rpc:            db files
    netgroup:       nis
</pre>

Notice the 'hosts:'  We need to add 'mdns' to the end so that the line looks
like:

<pre>
    hosts:          files mdns4_minimal [NOTFOUND=return] dns <b>mdns</b>
</pre>

What does this do? Why there are two "mdns" items?
The second mdns is needed ot make the ".local" domain work.
"The minimal versions [the mdns4_minimaal] will always deny to resolve host
names that don't end in .local or addresses that aren't in the range 169.254.x.x"


## Replacement for the Mobile App

The mobile application will not work.  It expects to talk with the production
servers and doesn't know how to work with the EscapePod.  Instead, use Vector
Explorer by Wayne Venables at:

* [https://weekendrobot.com/vectorexplorer/](https://weekendrobot.com/vectorexplorer/)

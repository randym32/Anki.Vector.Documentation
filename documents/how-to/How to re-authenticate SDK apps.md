## Introduction & Overvioew
With the EscapePod beta, for purposes of scope control, some robot function had
to be tabled until later. One of those was the HTTPS SDK.  If you're robot was
already authenticated with your SDK (that is, you had the certificates and
token needed) *and* you did **not** clear the user data to start using the
EscpadePod, then you're fine.  You don't need this.

If you haven't authenticated with the HTTPS SDK since you installed OSKR, or
you cleared your data as part of setting up the EscapePod,.. or are just
curious, this app note is for you.

This is how to get the certificate and SDK API guid so that your python SDK
apps, .NET SDK Apps, including Vector Explorer, can get work again with the
EscapePod.

Just a bit of fair warning: this process does still use the old Anki servers
for one step.  As mentioned at the top, the SDK sign-in / authentication is
will change in the future as the EscapePod matures.

You will need to know the robot name, serial number, and IP address.

The steps:

1. Get the certificate from the robot
2. Get the GUID
3. Update the sdk_config.ini with these

## Getting the certificate from the robot

The API .cert (certificate) file is actually on the robot in the
`/data/vic-gateway/`  folder.  If you read the python SDK source, the SDK gets
the certificate from the server.  During startup, the robot checks for the
existence of a certificate.  After a "clear user data", there won't one.  So
the robot creates one.  And, when it next talks with the cloud (such as part of
the onboarding steps to get an account linked to the robot), the certificate is
uploaded to the server.

You can copy from your robot `/data/vic-gateway/gateway.cert` file to your
`~/.anki_vector` folder.   You will need to rename it with the robot name and
serial number, with a pattern like:

    Vector-A1B2-007067cd.cert

I did it in one swoop with scp:

    scp root@192.168.1.123:/data/vic-gateway/gateway.cert ~/.anki_vector/Vector-A1B2-007067cd.cert

(The robot performs SDK calls without the certificate, although I'm not sure if
the SDK will have an error without out the certificate. If you're curious what
the cert is used for: it is used so that you can be sure that you're talking to
the real robot, not some sneaky imposter.)

## Getting a new GUID token

Next we need to get a "guid" for communication.  This is a succinct token that
Vector uses to know that the API commands are coming from someone authorized to
use the robot.

To get this guid token, run the attached python script.  You run it with a
command line like:

    python robot.py 192.168.1.123 guid

Changing the ip address, to the one for your robot.

You will be asked to give your email address and password pair that your anki
account  is in.  It will print out the guid after that.

For example:

    >python robot.py 192.168.1.123 guid
    Enter your email and password. Make sure to use the same account that was used to set up your Vector.
    Enter Email: someone@someplace.org
    Password:
    ZLIO/y48QzeXynjiORrxgQ==

That funny text on the line below the password is the guid that we need to
complete the .ini  file.

The script passes username, and password to the old Anki server.  The server
knows how to validate your account, and what the shared secret is with the
robot.  And then sends back information that is used to create the guid.

Vector doesn't know you're account or password.  The Vector serial name isn't
passed to the old Anki servers when the guid is made.


## Putting this all together in the sdk_config.ini file

Now let's, edit the '~/.anki_vector/sdk_config.ini'

Open it up.  First look to see if there is a section already with your robots
serial number, you will need to remove it.

Next, lets create a  new section for this robot.  The  section name is the
serial number of the robot.  The section will look like this when we're done:

    [007067cd]
    cert = /Users/JoeUser/.anki_vector/Vector-A1B2-007067cd.cert
    ip = 192.168.1.123
    name = Vector-A1B2
    guid = ZLIO/y48QzeXynjiORrxgQ==

Change `007067cd` to the serial number of your robot Give it your robot's name.

    name = Vector-A1B2

And put in the IP address for your robot:

    ip = 192.168.1.124

Next, in the new section update the path to the cert file that you downloaded
in step 1:

    cert = /Users/JoeUser/.anki_vector/Vector-A1B2-007067cd.cert

Finally, add an entry for the guid that we received in the second section:

    guid = ZLIO/y48QzeXynjiORrxgQ==

## Final steps

After that, you should be able to use Vector Explorer, or any SDK program with
your robot.  If you run into trouble, double check:

 * the path and name of teh certificate file,
 * the guid
 * the robot IP address, and (of course)
 * the robot name

## Resources

Attached is the script created by Mike Corlett that we use to get the guid.
(It'd be cool if someone updated the script to do all the work so a human
didn't have to any .ini files.)

https://gist.github.com/randym32/16bde0ce2dda841336e3f9a250cca009 1

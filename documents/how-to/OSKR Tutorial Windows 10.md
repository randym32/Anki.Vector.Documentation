# OSKR Tutorial for Windows 10

Digital Dream Labs has released a product called "OSKR". This allows you to turn your Vector into, essentially, a "dev" bot.

This means you can install software onto him which allows you to edit files on him.

Soon, the source will be released and this wiki will contain build instructions.

Follow these intructions carefully, and read through them before starting. OSKR isn't easy stuff.

## Prerequesites

Windows 10 computer with Bluetooth support

### Get your Vector's serial number to give to DDL

1. In Google Chrome (this has to be Google Chrome), go to [Project Victor Web Setup](https://www.project-victor.org/noflow-devsetup).

2. It should show instructions and a "PAIR WITH VECTOR" button. If it says you need Chrome, go to `chrome://flags` in the URL bar and enable `Enable experimental web platform features`. Relaunch Chrome twice to make sure it got applied.

3. Turn on Vector and make sure he is at eyes.

4. Follow the instructions on the Vector web setup site. This may take many refreshes and reboots.

5. Once you are connected, type `logs` to download his logs.

6. Install this: [7-Zip (Windows)](https://www.7-zip.org/a/7z1900-x64.msi)

7. Once they are downloaded: press the arrow on the logs which have downloaded, press "Show in folder", right click on the file, go into the `7-zip` part of the right click menu, press "Open archive".

8. Your serial number is in `factory/log1`. To open this file, double press it and select Notepad.

9. The QSN and ESN are at the bottom. For instance, mine is `QSN=323339903 # ESN=0030a012`. Copy this and fill out the form Digital Dream Labs gave you in an email.

10. Wait for the OTA to be sent to you, then do the rest of the steps.

### Install Python

1. Python can be found at [https://python.org](https://python.org). Here is a direct link to Python 3.9.1.

2. [Python 3.9.1 Installer](https://www.python.org/ftp/python/3.9.1/python-3.9.1-amd64.exe)

3. When installing, make sure you check "Install Python 3.9.1 to PATH". Just press "Next" on all the other menus.

### Download your OSKR OTA, find IP address, run Python server

1. Download your OSKR OTA with the link you have recieved from Digital Dream Labs. Open this link in the browser of your choice, and make sure it is saved in your Downloads folder.

2. Open Powershell. To do this: open the start menu, type "Powershell", then click the first thing that shows up.

3. Type `ipconfig`. This shows the network interface information. Your IP address is usually in the top section, next to "IPv4 Address ...". It usually starts with "192.168" or "10.".

4. In the same Powershell window, type `cd Downloads`, then type `py -m http.server`. `cd` changes your directory to the directory provided and `py` is Python. In this case, we have just told Python to open an HTTP server.

5. To test that you have the correct IP address and the server is running correctly, open a browser window and put the IP address you got into the browser URL bar followed by `:8000` (for instance, my local IP is 192.168.1.3. I would type `192.168.1.3:8000`). When you hit enter, there should be a directory listing.

6. If there is no directory listing, try a different IP address in `ipconfig` and make sure the server shows that it is running at `0.0.0.0:8000`.

### Test your server

1. Download this: [latest.ota](http://ota.global.anki-services.com/vic/prod/full/latest.ota)

2. Make sure your Vector is turned on and at eyes/phone onboarding screen.

3. Put Vector into recovery by holding his button for 15 seconds on the charger. Keep holding it until the light turns green or purple again. He should be on `anki.com/v` after a while.

4. In Google Chrome (this has to be Google Chrome), go to [Project Victor Web Setup](https://www.project-victor.org/noflow-devsetup).

5. It should show instructions and a "PAIR WITH VECTOR" button. If it says you need Chrome, go to `chrome://flags` in the URL bar and enable `Enable experimental web platform features`. Relaunch Chrome twice to make sure it got applied.

6. Follow the instructions on the web setup. If it is giving you trouble, try reloading the page and rebooting Vector (make sure you use the 15 second button hold method so he stays in recovery). It may take many attempts.

7. It should put you on a terminal. To connect him to Wi-Fi, type `wifi-connect ssid password`. Replace `ssid` with your network name and `password` with your network password. If you have a space in either of those, put quotations (") around it. For instance, one would be `wifi-connect "The Man Cave" pA55w4d`

8. Once connected to Wi-Fi, type `ota-start http://ipaddress:8000/latest.ota`. Replace `ipaddress` with your computer's actual IP address (for instance, mine would be `ota-start http://192.168.1.3:8000/latest.ota`). What you are doing here is installing the latest production OTA, and this isn't OSKR yet. This is like simulating what the phone app does when you first setup Vector.

9. If all has gone well, he should be at eyes. If he errors out, Vector may not be on the same network as your computer or you have already applied the OSKR unlock to your Vector.

### Installing OSKR unlock

1. Make sure your Vector is at eyes. Do NOT put him into recovery this time.

2. Go to this site in Google Chrome. [Project Victor Web Setup](https://www.project-victor.org/noflow-devsetup)

3. Pair with Vector by following the instructions on the site. It will dump you to a terminal.

4. If he isnt connected to Wi-Fi, type `wifi-connect ssid password`. Replace `ssid` with your network name and `password` with your network password. If you have a space in either of those, put quotations (") around it. For instance, one would be `wifi-connect "The Man Cave" pA55w4d`

5. Time to install the OSKR unlock OTA. Type `ota-start http://ipaddress:8000/serial.ota`. Replace `ipaddress` with your computer's actual IP address and `serial` with the bot's serial number/name of the OTA (for instance, mine would be `ota-start http://192.168.1.3:8000/0060059b.ota`).

6. I recommend telling him to go to sleep while this is installing.

### Installing OSKR firmware

After the unlock application, he should boot into recovery with the "OSKR" splash screen.

Congratulatons! Your bot is now unlocked!

Now we need to put on firmware which will allow you to do all the cool dev stuff.

1. Go to this site in Google Chrome. [Project Victor Web Setup](https://www.project-victor.org/noflow-devsetup)

2. Pair with Vector by following the instructions on the site. It will dump you to a terminal.

3. Download this: [lkg.ota](https://ota.global.anki-dev-services.com/vic/master-oskr/g8p45w5tfuma3g46/full/lkg.ota)

3. 8. Once connected to Wi-Fi, type `ota-start http://ipaddress:8000/lkg.ota`. Replace `ipaddress` with your computer's actual IP address (for instance, mine would be `ota-start http://192.168.1.3:8000/lkg.ota`).

4. Once you are done, user data will be cleared. Set him up with the Vector Robot app. If you are unable to do so, try using this .bat file (use PROD env): [VectorSetup.bat](https://cdn.discordapp.com/attachments/527877393516462105/783925717351792650/VectorSetup.bat)

### Getting in

You are now running OSKR firmware. This means you can go in via SSH and do a whole bunch of cool stuff.

1. In Google Chrome (this has to be Google Chrome), go to [Project Victor Web Setup](https://www.project-victor.org/noflow-devsetup).

2. It should show instructions and a "PAIR WITH VECTOR" button. If it says you need Chrome, go to `chrome://flags` in the URL bar and enable `Enable experimental web platform features`. Relaunch Chrome twice to make sure it got applied.

3. Turn on Vector and make sure he is at eyes.

4. Follow the instructions on the Vector web setup site. This may take many refreshes and reboots.

5. Once you are connected, type `logs` to download his logs.

6. Make sure you have this installed: [7-Zip (Windows)](https://www.7-zip.org/a/7z1900-x64.msi)

7. Once they are downloaded: press the arrow on the logs which have downloaded, press "Show in folder", right click on the file, go into the `7-zip` part of the right click menu, press "Open archive".

8. Your SSH key is in `data/ssh/id_rsa-Vector-####`. Drag this to your desktop, and make sure you leave the .pub one alone.

9. Open Powershell (Start menu, type "Powershell", press first thing that shows up)

10. In Powershell, type `cd Desktop`, then `ssh -i id_rsa-Vector-#### root@vectorip`. Replace `####` with the actual Vector ID and `vectorip` with Vector's actual IP address. Vector's IP address can be found in CCIS. You can go to this by placing him on the charger, double pressing his button, then lifting his lift up then down. His IP address will be the number in green (or yellow idk. im colorblind). For instance, mine would be `ssh -i id_rsa-Vector-H9P8 root@192.168.1.4`. When you are typing it, and you are in the middle like `ssh -i id_rsa-V`, you can press tab for it to auto complete.

11. If you get any error: make sure you are on the same network as Vector. If it can't find the command `ssh`, install [Git Bash](https://git-scm.com/download/win). You can open Git Bash and run the same `cd Desktop` and `ssh -i id_rsa-Vector-#### root@vectorip`

<!-- I would say to use PuTTy but I haven't tried to use that yet -->



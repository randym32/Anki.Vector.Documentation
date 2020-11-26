# Hardware error codes

If something has gone wrong, an error will appear on Vector's face. These error happen if Vector's hardware is bad, but some of them could also be software.

801

* Rampost was unable to communicate with the body board at boot. This will show up before an 898 or 899 error. If the board shows just a purple light and won't turn off, you need to wait for his battery to die. After that, turn him back on. If there is still a purple light, there could be a hardware issue with the body board.

870-895

* Body board has a specific hardware fault. For all of these, try a reboot. If that doesn't work, your Vector probably needs some fixin'.

870

* The front right microphone is not working correctly.

871

* The front left microphone is not working correctly.

872

* The back right microphone is not working correctly.

873

* The back left microhpone is not working correctly.

// I'm not sure if 870-873 actually show up as I have seen boards get through rampost without the backpack board connected.

890

* The front right cliff sensor is not working correctly.

891

* The front left cliff sensor is not working correctly.

892

* The back right cliff sensor is not working correctly.

893

* The back left cliff sensor is not working correctly.

894

* The front ToF sensor is not working correctly.

895

* The touch sensor is not working correctly.

896(?)-897

* Seems to be Whiskey specific. It seems to only show in their dev recovery and they work fine in normal firmware, so this doesn't seem to be a worry.

898

* There was an error when trying to communicate with the body board. If the board shows just a purple light and won't turn off, you need to wait for his battery to die. After that, turn him back on. If there is still a purple light, there could be a hardware issue with the body board.

899

* The firmware was unable to find the body. If the board shows just a purple light and won't turn off, you need to wait for his battery to die. After that, turn him back on. If there is still a purple light, there could be a hardware issue with the body board.

950

* This error will only occur on a Whiskey. The software is unable to open the extra ToF sensors. It is possible that one or both of the sensors are broken. 
* This can be fixed with an EMR/OEM swap. Instructions soon

960

* IMU hardware failed.

970

* The Wi-Fi hardware failed.

980-981

* An error occured when trying to communicate with the camera. If he is stuck on this error, go to recovery and clear user data. If he is still stuck, the camera may not be soldered on well or it could be broken.

990

* Vic-anim is unable to open the display for writing. This is something you will probably never see.

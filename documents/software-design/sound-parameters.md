# Sound Parameters

Vector's sound engine is designed to give a more life-like quality to his sounds.
It does this by varying the sounds it plays when an [audio event](sound-events.md)
is received by the audio engine.  Instead of playing a single, fixed sound file,
a sequence of semi-randomized sounds is played.  Some events
have many possible sequences that could be played.  The audio engine selects
the sequence based primarily on Vector’s current level of stimulation.  


## Input parameters (inputs from the animation system and engine)

_Audio parameters_ are settable values passed to the audio engine, guiding it
in how it selects and plays the sounds.
(These are called "game parameters" in Wwise parlance.)  Vector mainly
uses these to adjust the sounds based on his current mood and activity.  Like
the action, these parameters are on a per object (within the audio engine) basis.

The sound engine is connected to the high-level state of the other major robot
sub-systems, so that the sounds could reflect what Vector’s body is doing, his
mood, emotional state,  level of stimulation, and even to respond to the environment.
Although many parameters are provisioned in the soundbanks, only few are used:
they were too hard to get right.

The parameters linked to the emotion state & mood:

| Parameters     |Id|Description|
|----------------|--|-----------|
|Robot_Vic_Confident|2193267925|This captures the emotion dimension "confidence" |
|Robot_Vic_Happy  |1391855411|This captures the emotion dimension "happy"|
|Robot_Vic_Held_Trust|1255095877|This captures the emotion dimension "trust”|
|Robot_Vic_Purr_Level|3113529605||
|Robot_Vic_Social  |240199822|This captures the emotion dimension "social"|
|Robot_Vic_Stimulation|651061178|"This stimulation variable is a distillation of all possible environmental affects Vector experiences. For example, ‘hey Vector’ or touch automatically triggers a 1.0, getting stuck drop the stim to about 0.5, etc. .. We adapted the audio system to gradually lower in probability and volume as the stimulation level lowered. The goal being that active Vector users get a more lively sounding robot, and Vectors left on but not being interacted with wouldn't be so chirpy." (Ben Gabaldon)|

The parameters linked to the body’s posture and movement:

| Parameters     |Id|Description|
|----------------|--|-----------|
|Robot_Vic_Head_Accelerate|2691629051|How fast the head is changing speed.|
|Robot_Vic_Head_Position |1549905781|This captures the heads position: where it is looking.|
|Robot_Vic_Head_Speed |4244799613|This is linked to the speed that the head is moving at, and the direction it is moving in.|
|Robot_Vic_Lift_Accelerate|1685856300|How fast the lift is changing speed.|
|Robot_Vic_Lift_Position|4014791842|This is the position of the lift.|
|Robot_Vic_Lift_Speed|2317283412|This is linked to the speed that the lift is moving at, and the direction it is moving in.|
|Robot_Vic_Tread_Accelerate|496587279|How fast the treads are changing speed.|
|Robot_Vic_Tread_Speed|724346585|This is linked to the speed that the treads are moving, and the direction they are moving in.|
|Robot_Vic_Tread_Spin_Speed|3313708352|This is linked to the speed that the robot is spinning, and the direction it is spinning in.|


| Parameters |Id|Description|
|------------|--|-----------|
|Dev_Squawk_Volume|847280258||
|Dev_Tone_Freq|2324555758||
|Event_Volume|3530059848||
|External_Shape|1292394150||
|External_Speed|732885492||
|Robot_Alexa_Volume_Alerts|522470314||
|Robot_Alexa_Volume_Master|3289463297||
|Robot_Vic_Environment_Ambient_Volume|344494516||
|Robot_Vic_How_Old_Speed|4000308525||
|Robot_Vic_Meter_Bus_SFX|1248968661||
|Robot_Vic_Meter_Bus_TTS|913563323||
|Robot_Vic_Meter_Bus_VO|3946120957||
|Robot_Vic_Planning|954718164||
|Robot_Vic_Screen_Shift_Interpolation_Time|1775375659||
|Robot_Vic_Sdk_Volume|995643170||
|Robot_Vic_Shaking|2064796514||
|Robot_Vic_Timer_Countdown|165240122||
|Robot_Vic_Volume_Animation|1008373634||
|Robot_Vic_Volume_Behavior|359550870||
|Robot_Vic_Volume_Master|1036978186|This is linked to the volume preference setting, controlled by the mobile application (or SDK).|
|Robot_Vic_Volume_Procedural|346758509||
|Ss_Air_Fear|1351367891||
|Ss_Air_Freefall|3002758120||
|Ss_Air_Fury|1029930033||
|Ss_Air_Month|2648548617||
|Ss_Air_Presence|3847924954||
|Ss_Air_RPM|822163944||
|Ss_Air_Size|3074696722||
|Ss_Air_Storm |3715662592||
|Ss_Air_Timeofday |3203397129||
|Ss_Air_Turbulence|4160247818||

## Derived sound settings

Many events trigger a sound which is made of a sequence of smaller sounds.
In some cases there are several possible sequences, selected by a switch setting.

Those inputs above are smashed and mashed down into a switch setting, that
the sound banks used to select from different sound alternatives.
A switch, for those familiar with software, is a variable that has an enumeration type.
Except that, in Vector’s sound banks, the enumeration is unique in each case.


|  Parameter | Switch States|Ids| Description|
|------------|--------------|---|----------|
|Robot_Vic_Head_Speed|Robot_Vic_Head_Direction_Down<br>Robot_Vic_Head_Direction_Up|3234804922<br>123512153||
|Robot_Vic_Lift_Speed|Robot_Vic_Lift_Direction_Down<br>Robot_Vic_Lift_Direction_Up|3238791869<br>807633034||
|Robot_Vic_Screen_Shift_Interpolation_Time|Shift_Short<br>Shift_Long|3156794696<br>3265274760||
|Robot_Vic_Stimulation| Stim_01<br>Stim_02<br>Stim_03<br> Stim_04|446181668<br>446181671<br>446181670<br>446181665||
|Robot_Vic_Tread_Spin_Speed|Robot_Vic_Tread_Drive<br>Robot_Vic_Tread_Spin|4283612440<br>2961118536||
|Robot_Vic_Tread_Speed|Robot_Vic_Tread_Backward<br>Robot_Vic_Tread_Forward|3258446947<br>1541107887||


## Change history synopsis


|Date|Change|
|----|------|
|2021-2-26|Created|
|2021-7-3|Added ids|
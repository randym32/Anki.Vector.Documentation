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

| Parameters |Description|
|------------|-----------|
|Robot_Vic_Confident|This captures the emotion dimension "confidence" |
|Robot_Vic_Happy|This captures the emotion dimension "happy"|
|Robot_Vic_Held_Trust|This captures the emotion dimension "trust”|
|Robot_Vic_Purr_Level||
|Robot_Vic_Social|This captures the emotion dimension "social"|
|Robot_Vic_Stimulation|"This stimulation variable is a distillation of all possible environmental affects Vector experiences. For example, ‘hey Vector’ or touch automatically triggers a 1.0, getting stuck drop the stim to about 0.5, etc. .. We adapted the audio system to gradually lower in probability and volume as the stimulation level lowered. The goal being that active Vector users get a more lively sounding robot, and Vectors left on but not being interacted with wouldn't be so chirpy." (Ben Gabaldon)|

The parameters linked to the body’s posture and movement:

| Parameters |Description|
|------------|-----------|
|Robot_Vic_Head_Accelerate|How fast the head is changing speed.|
|Robot_Vic_Head_Position|This captures the heads position: where it is looking.|
|Robot_Vic_Head_Speed|This is linked to the speed that the head is moving at, and the direction it is moving in.|
|Robot_Vic_Lift_Accelerate|How fast the lift is changing speed.|
|Robot_Vic_Lift_Position|This is the position of the lift.|
|Robot_Vic_Lift_Speed|This is linked to the speed that the lift is moving at, and the direction it is moving in.|
|Robot_Vic_Tread_Accelerate|How fast the treads are changing speed.|
|Robot_Vic_Tread_Speed|This is linked to the speed that the treads are moving, and the direction they are moving in.|
|Robot_Vic_Tread_Spin_Speed|This is linked to the speed that the robot is spinning, and the direction it is spinning in.|


| Parameters |Description|
|------------|-----------|
|Event_Volume||
|External_Shape||
|External_Speed||
|Robot_Alexa_Volume_Alerts||
|Robot_Alexa_Volume_Master||
|Robot_Vic_Environment_Ambient_Volume||
|Robot_Vic_How_Old_Speed||
|Robot_Vic_Screen_Shift_Interpolation_Time||
|Robot_Vic_Meter_Bus_SFX||
|Robot_Vic_Meter_Bus_TTS||
|Robot_Vic_Meter_Bus_VO||
|Robot_Vic_Planning||
|Robot_Vic_Sdk_Volume||
|Robot_Vic_Shaking||
|Robot_Vic_Timer_Countdown||
|Robot_Vic_Volume_Animation||
|Robot_Vic_Volume_Behavior||
|Robot_Vic_Volume_Master|This is linked to the volume preference setting, controlled by the mobile application (or SDK).|
|Robot_Vic_Volume_Procedural||
|Ss_Air_Fear||
|Ss_Air_Freefall||
|Ss_Air_Fury||
|Ss_Air_Month||
|Ss_Air_Presence||
|Ss_Air_Rpm||
|Ss_Air_Size||
|Ss_Air_Storm||
|Ss_Air_Timeofday||
|Ss_Air_Turbulence||
|2324555758||
|847280258||

## Derived sound settings

Many events trigger a sound which is made of a sequence of smaller sounds.
In some cases there are several possible sequences, selected by a switch setting.

Those inputs above are smashed and mashed down into a switch setting, that
the sound banks used to select from different sound alternatives.
A switch, for those familiar with software, is a variable that has an enumeration type.
Except that, in Vector’s sound banks, the enumeration is unique in each case.


|  Parameter | Switch States| Description|
|------------|--------------|-----------|
|Robot_Vic_Head_Speed|Robot_Vic_Head_Direction_Down<br>Robot_Vic_Head_Direction_Up||
|Robot_Vic_Lift_Speed|Robot_Vic_Lift_Direction_Down<br>Robot_Vic_Lift_Direction_Up||
|Robot_Vic_Screen_Shift_Interpolation_Time|Shift_Short<br>Shift_Long||
|Robot_Vic_Stimulation| Stim_01<br>Stim_02<br>Stim_03<br> Stim_04||
|Robot_Vic_Tread_Spin_Speed|Robot_Vic_Tread_Drive<br>Robot_Vic_Tread_Spin||
|Robot_Vic_Tread_Speed|Robot_Vic_Tread_Backward<br>Robot_Vic_Tread_Forward||


## Change history synopsis


|Date|Change|
|----|------|
|2021-2-26|Created|

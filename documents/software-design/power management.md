---
title: Power management behaviors
summary: The behaviors related to turning off, handling very low-battery,
         sleeping, and other battery-related items.
         (These are self-maintenance behaviors)
---

This note describes the power management-related behaviors.
Please refer to the [Technical Reference Manual](index.md#TRM)
for a description of Vector's internal power states, management, and sleep debt.

The main power management behaviors are launched at a very high-level.
These are launched by the *ModeSelector* (class *DispatcherStrictPriority*)
behavior.  This behavior is invoked by:

* [*InitNormalOperation* behavior](startup behavior.md) during start of normal
  behavior
* *AcousticTestMode* behavior during aoustic testing at the factory
* *DevBaseBehaviorInternal* behavior during start of developer mode


![Power management behavior tree](power management.svg#zoom)
*Figure: The power management behavior tree*

The behavior file is located at:

    behaviors\victorBehaviorTree\modeSelector.json

The behavior tree system gives things in explicit priority order.   The higher
item in the list has more priority than the lower; when an item calls out to
other nodes, all of those still have higher priority than the items lower than
the original one.

The mode selector:

* Handle powering off (the highest priority)
* Alexa-related behaviors (not related to power management)
* Handle overheating (in emergency mode)
* SDK override (not related to power management)
* Being quiet related behaviors (not related to power management)
* Handle low battery and attempt to return to charger... if unable, turn off
* A sleep/[quiet state](quiet mode.md) manager.  Regular behaviors and
  interactions are started in this behavior tree, so are at the lowest priority.


## Powering off

The highest priority behavior is the *SingletonPoweringRobotOff* (class
*PoweringRobotOff*) behavior, that animates Vector while he is the process of
turning off.


| Name | Type | Value   | Description|
|------|------|---------|------------|
|powerButtonHeldToActivate_ms|int|250 ms|The minimum time that the power button must be held down to activate the power off sequence.|
|powerOnAnimName|animation|anim_power_offon_01|The animation to play if the button is released and Vector will resume.|
|powerOffAnimName|animation|anim_power_onoff_01|The animation to play while powering off.|

*Table: _PoweringRobotOff_ configuration parameters*

If the power button is released before Vector has turned off, the behavior
begins the process of resuming, 

The animation reference is unusual.  It doesn't refer to the trigger of an
animation group.  Instead it refers to a specific animation.

## Sleep

At the opposite end -- the *lowest* priority -- is the *SleepCycle* (class
*SleepCycle*) behavior.  The behavior file is located at:

    behaviors/victorBehaviorTree/highLevelDelegates/sleeping/sleepCycle.json

This behavior arbitrates between:

* Vector autonomously exploring
* Interacting with a person (outside of Alexa).
* And going into a sleep state

If Vector has no reason to sleep, this behavior lets the *CoordinateInHabitat*
behavior.  If it decides to sleep (the decision is made in the C++ code)
It initiates the *FindHomeForSleeping* behavior to drive to the charging dock,
if possible, to sleep.  (In turn it invokes
[*MandatoryPhysicalReactions*](mandatoryPhysicalReactions.md) to respond to 
environmental hazards while driving around.)


This has a condition that keeps it in sleep, even if there is a higher
priority interaction, if:

* The battery level is low,
* The temperature is high, or
* Charging is stopped because it is too hot.


Depending, it will initiate the looking for home to go to sleep.
This is the *FindHomeForSleeping* behavior.

Things that wake Vector up from the different kinds of sleep:

| Sleep state   | Things that wake Vector|
|---------------|------------------------|
|HeldInPalmSleep|Being jolted, touched, picked up (out of the hand), SDK interaction, the timer, and voice commands.|
| LightSleep    |Being jolted, poked, touched, or picked up; any sound or the lights coming on; SDK interaction, the timer, and voice commands.|
| DeepSleep     |Being touched, or picked up; SDK interaction, the timer, and voice commands. |

*Table: That wake Vector from sleep.*

This behavior includes a decision tree that sets a `reason` code for based on
sensors that have trigger.  That reason code is used above.  By editting this
behavior's decision tree, you can adjust how sensitive he is to conditions like
touch, poking, illumination to wake him from sleep.

Note: In power save mode -- a lower sleep state -- the camera is turned off, so
Vector is not sensitive to light.

### Driving to the charging dock to sleep

When Vector is going into a sleep state, *FindHomeForSleeping* (class
*DispatcherStrictPriority*) behavior to drive to the charging dock,
if possible, to sleep.  The behavior file is located at:

    behaviors/victorBehaviorTree/highLevelDelegates/sleeping/findHomeForSleeping.json

This behavior stops whatever else is going on, and runs a subset of navigation
and driving related behaviors.

## Emergency Mode

Emergency mode is quite complex, and handles conditions where:

* The battery level is low,
* The temperature is high, or
* Charging is stopped because it is too hot.

The way to exit emgency mode is for the battery level to rise above the low
threshold, and for temperature to cool below the hot threshold.

This is controlled by the *EmergencyMode* (class *DispatcherQueue*) behavior.

![Emergency mode](emergency mode.svg#zoom)
*Figure: The emergency behavior tree*

The behavior file is located at:

    behaviors/victorBehaviorTree/emergencyMode/emergencyMode.json

### Animation feedback

The behavior coordinates with working with other social interactions,
albeit in a restricted manner.  If the trigger word is heard, it doesn't
stream the audio to the voice server.  Instead it:

1. Plays the *VC_ListeningGetIn* animation, then
2. Plays the *StreamingDisabledButWithLight* animation to indicate that streaming is disabled, and filly
3. Sends the *Play__Robot_Vic_Sfx__Wake_Word_On* audio event to play a feedback sound.
4. It also links with the following animation to show the reason why

Emergency mode uses the *EmergencyModeAnimDispatcher* (class *DispatcherQueue*)
behavior to play different animations based on the the emergency condition:

* If the battery is low, it will trigger the *ChargerDockingSorryButLowBattery*
  animation.
* If the temperature is high, or too hot charge, it will trigger the
  *HighTemperatureWarningFace* animation.
  
The behavior file is located at:

    behaviors/victorBehaviorTree/emergencyMode/emergencyModeAnimDispatcher.json

If Vector is in picked up, or otherwise off his treads (but not being held),
he plays the *ChargerDockingRequestPickup* animation.  This is done in the
*EmergencyModeInAir* behavior.  The behavior file is located at:

    behaviors/victorBehaviorTree/emergencyMode/emergencyModeInAir.json

### Returning to the charging dock

There are a couple of behaviors that try to cause Vector to drive back to the
charging dock.  These run a subset of navigation and driving related behaviors
to drive to the charging dock. The first is the *EmergencyModeOffCharger* (class 
*DispatcherStrictPriority*).  The behavior file is located at:

    behaviors/victorBehaviorTree/emergencyMode/emergencyModeOffCharger.json

The second is the *QuietModeEmergencyModeGoHome* (class 
*DispatcherStrictPriority*), which would be invoked while in quiet mode.
_Commentary:  This behavior appears like it should
not run; the same conditions that would trigger it would also trigger the much
higher priority *EmergencyMode* behavior.  This behavior should be checked
out and considered for removal._

## Change history synopsis

|Date|Change|
|----|------|
|2020-11-30|Created|
|2020-12-1 |Quiet mode's emergency mode, and trigger word animation|


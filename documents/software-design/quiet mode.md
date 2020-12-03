---
title: Quiet mode behaviors
summary: The behaviors related to turning off, handling very low-battery,
         sleeping, and other battery-related items.
         (These are self-maintenance behaviors)
---

The quiet mode is when Vector's has been asked to be silent, either
nicely ("be quiet") or abusively ("shut up").

## Quiet Mode

The *QuietMode* behavior is when Vector's has been asked to be silent,
nicely ("be quiet") using the `imperative_quiet` user intent.

![Quiet mode behavior tree](quiet mode.svg#zoom)
*Figure: Quiet mode behavior tree*


It *QuietModeEmergencyModeGoHome* see [power management](power management.md)
for a description of emergency mode.

The *BeQuietAnims* behavior is used to trigger the *Feedback_BeQuiet* animation,
and lowers the Vector's drowsy head, using the *PutHeadDownInternal* behavior.

Thereafter the *BeQuietLoop* is used play one of three animations:

* The *ObservingIdleEyesOnly* animation is played while Vector sits quietly and
  looks around.
* The *GoToSleepGetIn* animation is played when Vector goes to sleep,
* The *GoToSleepSleeping* animation is played while Vector sleeps.

## ShutUp mode

The *ShutUpMode* behavior is variation of quiet mode, used when Vector's has
been asked to "shut up" (the `imperative_shutup` user intent).

![Shut up mode behavior tree](shutup.svg#zoom)
*Figure: Shut up mode behavior tree*

The main difference is the intent that triggers is, and the animation response.
Thereafter, this mode reused the same *BeQuietLoop* used by the quiet mode.

## Change history synopsis

|Date|Change|
|----|------|
|2020-12-1|Created|


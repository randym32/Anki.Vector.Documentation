---
title: Power management behaviors
summary: The behaviors related to turning off, handling very low-battery,
         sleeping, and other battery-related items.
         (These are self-maintenance behaviors)
---

The main power management behaviors are launched at a very high-level.
These are launched by the `ModeSelector` (class `DispatcherStrictPriority`)
behavior.  This behavior is invoked by:

* [`InitNormalOperation' behavior](startup behavior.md) during start of normal
  behavior
* `AcousticTestMode` behavior during aoustic testing at the factory
* `DevBaseBehaviorInternal` behavior during start of developer mode


~[Power management behavior tree](power management.svg)

Something something something

This is a describto

## Power on

When Vector powers on

## Emergency Off

There are a small number of high priority behaviors to handle "emergency"

1. Things that pose a significant to Vector, like an overheated battery
2. Things that pose a risk to play, like running out of power
3. ??

## Sleep

??

## Charging ?

??Yeah

## Change history synopsis

|Date|Change|
|----|------|
|2020-11-29|Created|


---
title: Communication trouble behaviors
summary: These behaviors play animations when there is communication problems.
         (These are self-maintenance behaviors)
---

These behaviors are not called by a behavior tree configuration file.
Instead they are are invoked by the internal behavior implementation,
in the *BehaviorReactToVoiceCommand* class.

## No Wifi behavior

The *NoWifi* (class *DispatcherQueue*) behavior is used to animate Vectors
face when he is unable to connect to a Wifi SSID.

![No Wifi behavior diagram](noWifi.svg#zoom)
*Figure: The No Wifi behavior tree*

The behavior file is located at:

    behaviors/victorBehaviorTree/noWifi.json

The behavior will play three animations:

1. The *NoWifiGetIn* animation when the behavior starts
2. The *NoWifiSearching" animation while Vector is looking for a Wifi SSID;
   This will play the *face_nowifi_signal* sprite sequence.
3. The*NoWifiIcon* animation when the above animation completes
   This will play the *face_nowifi_icon* sprite sequence.
4. Then the loop will repeat from step 2.   


## No Cloud behavior


The *NoCloud* (class *DispatcherQueue*) behavior is used to animate Vectors
face when he is able to connect to a Wifi SSID, but unable to connect to the
remote server.

![No Cloud behavior diagram](noCloud.svg#zoom)
*Figure: The No Cloud behavior tree*

The behavior file is located at:

    behaviors/victorBehaviorTree/noCloud.json


The *NoCloudAnim* behavior is used to animate the face.
The behavior will play two animations:

1. The *NoCloudGetIn* animation when the behavior starts.  Note that this is
   same as the *NoWifiGetIn* animation group.
2. The *NoCloudIco*" animation will loop thereafter.
   This will play the *face_nowifi_trouble_icon* sprite sequence.


The *NoCloudAttention* is used to transfer attention back(?)
to the previous task.

## Other variations

Curiosly there is another animation -- the *anim_cloud_icon* animation -- this
not used.  It is not part of an animation group, but probably was part of the
*NoCloudIcon* animation group.  It uses a *face_nocloud_icon*  sprite animation.


## Change history synopsis


|Date|Change|
|----|------|
|2020-12-2|Created|

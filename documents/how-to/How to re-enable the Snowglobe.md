# How to bring back the Snowglobe effect

It came up in the forums that Vector no longer played the SnowGlobe effect when
shaken.  Here is how to re-enable it.

## Preparation

You'll have to know how to SSH in, make the file system modifiable and edit a file.  To make the file system modifiable:

    mount -o rw,remount /

You will need to edit the following file:

    /anki/data/assets/cozmo_resources/config/engine/behaviorComponent/behaviors/victorBehaviorTree/globalInterruptions.json

first, make it write able (you can skip this if you know how to override it in vi)

    chmod +w /anki/data/assets/cozmo_resources/config/engine/behaviorComponent/behaviors/victorBehaviorTree/globalInterruptions.json

## Edit the top list of behaviors

Next edit the file:

    vi /anki/data/assets/cozmo_resources/config/engine/behaviorComponent/behaviors/victorBehaviorTree/globalInterruptions.json

Look for the lines

```json
    "WeatherResponses",
    "TakeAPhotoCoordinator",
    "ReactToRobotShaken",
    "ReactToTouchPetting",
```

Change the line

    "ReactToRobotShaken",
to 

    "ReactToRobotShakenSnowGlobe",

You can also leave both.  The first item has higher priority.

## Adjusting the shake threshold

you can tweak the threshold for the shaking:

    /anki/data/assets/cozmo_resources/config/engine/behaviorComponent/behaviors/victorBehaviorTree/reactions/reactToRobotShakenSnowGlobe.json

Look for the block

```json
  "wantsToBeActivatedCondition":
  {
    "conditionType" : "RobotShaken",
    "minAccelMagnitudeThreshold" : 16000
  }
```
  
Change the "16000" a lower or higher number for the threshold.

The robot shaken file has a similar config:

    /anki/data/assets/cozmo_resources/config/engine/behaviorComponent/behaviors/victorBehaviorTree/reactions/reactToRobotShaken.json

Look for the same block as above, and change the threshold.

If you leave both "ReactToRobotShaken" and "ReactToRobotShakenGlobe", have the
first item with a higher number.
If it is lower, it will always win.

## Reboot 

Finally you have to reboot for the updates to load and take effect.

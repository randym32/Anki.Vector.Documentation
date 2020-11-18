## Console Variables

Console Variables are part of the developer build.
They allow the developer to test, diagnose, and tweak (inject data into) the various modules.

This note is to help gather a description of each of console variables.
This format lets us gather information on them, and help understand where they
fit in.

These tables are not suitable for the TRM at this time; they may go better in
the software design description in the future.

Note: the k seems to be dropped or optional in matching


### A/B Testing console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kForceDisableABTesting|      |       |             |
|          |      |       |             |
|          |      |       |             |

### AIWhiteboard console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kBW_PossibleObjectClose_mm|      |       |             |
|          |      |       |             |

### Alexa console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kAcousticTestMode|      |       |             |
|kAlexaEnabledInAU|      |       |             |
|kAlexaEnabledInUK|      |       |             |
|kAlexaHackCheckForSystemClockSyncPeriod_s|      |       |             |
|kAlexaIdleDelay_s|      |       |             |
|kAlexaMaxIdleDelay_s|      |       |             |
|kAllowAudioOnCharger|      |       |             |
|kDEV_ONLY_EnableAlexaTemplateRendererStub|      |       |             |
|kLogAlexaDirectives|      |       |             |
|kNotchPower|      |       |             |


### Alexa.Init console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kDumpAlexaTriggerAudio|      |       |             |
|          |      |       |             |
|          |      |       |             |


### Alexa.Messaging console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kLogAlexaMessages|      |       |             |
|kStealAlexaWakewordAudio|      |       |             |


### Animation console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kShouldPreCacheSprites|      |       |             |
|kEyeDartFocusValue_pix|      |       |             |
|kIgnoreAnimWhitelist|      |       |             |

### AnimationStreamer console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kEnableBackpackLightsTrack|      |       |             |
|kShouldDisplayPlaybackTime|      |       |             |


### AnimationStreamer.System console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kDisplayCPUThrottling|      |       |             |
|kDisplayHighTemperature|      |       |             |
|kDisplayMemoryPressure|      |       |             |
|kThermalAlertTemp_C|      |       |             |


### Audio.AnimationStream console variables


| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kAudioAnimationOffset_ms| | | |

### Audio.KeepAlive console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kEnableKeepAliveEyeBlinkAudioEvents|      |       |             |
|kEnableKeepAliveEyeDartAudioEvents|      |       |             |
|kEnableKeepAliveEyeSquintAudioEvents|      |       |             |


### Audio.Microphone console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kNoiseFloorMin|      |       |             |
|kNoiseFloorRange|      |       |             |
|          |      |       |             |

### Audio.Procedural console variables


| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kEnableHeadProceduralMovement|      |       |             |
|kEnableLiftProceduralMovement|      |       |             |
|kEnableTreadProceduralMovement|      |       |             |
|kHeadCoolDown_ms|      |       |             |
|kHeadMovementThreshold_rpms|      |       |             |
|kLiftCoolDown_ms|      |       |             |
|kLiftMovementThreshold_rpms|      |       |             |
|kMaxHeadAccel_rpms2|      |       |             |
|kMaxHeadSpeed_rpms|      |       |             |
|kMaxLiftAccel_rpms2|      |       |             |
|kMaxLiftSpeed_rpms|      |       |             |
|kMaxTreadAccel_mmpms2|      |       |             |
|kMaxTreadSpeed_mmps|      |       |             |
|kMaxTurnSpeed_mmps|      |       |             |
|kTreadMovementThreshold_mmps|      |       |             |
|kTreadCoolDown_ms|      |       |             |


### BackpackLights console variables


| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kOfflineCheckFreq_ms|      |       |             |
|kOfflineTimeBeforeLights_ms|      |       |             |
|          |      |       |             |


### BasicActions.TurnTowardsObject console variables


| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kInsertWaitsInTurnTowardsObjectVerify|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Behavior.BehaviorGoHome console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kGoHome_VisualVerification_SaveImages|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Behavior.CheckForAndReactToSalientPoint console variables


| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kCFARTSP_CooldownOverride_sec|      |       |             |
|          |      |       |             |
|          |      |       |             |


### BehaviorCountingAnimation console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kSlowLoopBeginSize_loops|      |       |             |
|          |      |       |             |
|          |      |       |             |


### BehaviorDanceToTheBeatCoordinator console variables


| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kDancingCooldown_sec|      |       |             |
|          |      |       |             |
|          |      |       |             |


### Behaviors.BehaviorSystemManager console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kDebugBehaviorStack|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Behavior.EnrollFace console variables


| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kEnrollFace_TimeoutForReLookForFace_ms|      |       |             |
|          |      |       |             |
|          |      |       |             |


### BehaviorExploring console variables


| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kExploringPostBumpReferenceProb|      |       |             |
|kMinObjectWidthToBump_rad|      |       |             |
|kProbReferenceOnResume|      |       |             |


### BehaviorHighLevelAI console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kTimeMultiplier|      |       |             |
|          |      |       |             |
|          |      |       |             |


### Behavior.InteractWithFaces console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kInteractWithFaces_DriveForwardIdealDist_mm|      |       |             |
|kWiggle_ForwardDist_mm|      |       |             |
|          |      |       |             |


### Behavior.InternalStatesBehavior console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kDebugInternalStatesBehavior|      |       |             |
|          |      |       |             |
|          |      |       |             |


### Behavior.LookAroundInPlace console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kVizConeOfFocus|      |       |             |
|          |      |       |             |
|          |      |       |             |

### BehaviorPlannerTest console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kCubeDistance_mm|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Behavior.PutDownBlock console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kBPDB_finalHeadAngle_deg|      |       |             |
|          |      |       |             |
|          |      |       |             |


### Behavior.PuzzleMaze console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kPuzzleTimeout_sec|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Behavior.ReactToCliff console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kMaxNumRobotStopsBeforeGivingUp|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Behavior.ReactToHand console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kHandReaction_DriveForwardSpeed_mmps|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Behavior.ReactToPalmEdge console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kMaxNumInitialReactAttemptsBeforeGivingUp|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Behavior.TakeAPhoto console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kHeadAngleDeg|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Console console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kSaveModifiedConsoleVarsOnly|      |       |             |
|          |      |       |             |
|          |      |       |             |

### CpuProfiler console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kMessageProfilerDuration|      |       |             |
|maxProcessingTimePerDrop_ms|      |       |             |
|          |      |       |             |


### CubeLightDesign console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kLED1_s1_red|      |       |             |
|          |      |       |             |
|          |      |       |             |

### CubeSpinner console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kAdjustHeightOfSpinnerLift|      |       |             |
|kDedupTimeAfterLock_ms|      |       |             |
|kIReallyReallyWantToBreakCubeSpinner|      |       |             |

### Dev console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kForceDisableAnkiDevFeatures|      |       |             |
|          |      |       |             |
|          |      |       |             |

### DevBaseBehavior console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kDevDispatchAfterShake|      |       |             |
|          |      |       |             |
|          |      |       |             |

### DevSquawkBoxBehavior console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kLiftMovementDuration_s|      |       |             |
|          |      |       |             |
|          |      |       |             |

### DevViewLights console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kCubeTriggerIdx|      |       |             |
|          |      |       |             |
|          |      |       |             |

### DockingMethod(B:0 T:1 H:2) console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kDefaultDockingMethod|      |       |             |
|          |      |       |             |
|          |      |       |             |

### DockingTest console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kMaxNumAttempts|      |       |             |
|          |      |       |             |
|          |      |       |             |

### DriveToActions console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kEnablePredockDistanceCheckFix|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Face.KeepAlive console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kKeepAliveBlink_SpacingMaxTime_ms	|      |       |             |
|kKeepAliveBlink_SpacingMinTime_ms	|      |       |             |
|kKeepAliveEyeDart_DownMinScale	|      |       |             |
|kKeepAliveEyeDart_HotSpotPositionMultiplier	|      |       |             |
|kKeepAliveEyeDart_LongDistanceThresh_pix	|      |       |             |
|kKeepAliveEyeDart_LongShiftFraction1	|      |       |             |
|kKeepAliveEyeDart_LongShiftFraction2	|      |       |             |
|kKeepAliveEyeDart_LongSquashFraction1	|      |       |             |
|kKeepAliveEyeDart_LongSquashFraction2	|      |       |             |
|kKeepAliveEyeDart_MaxDistFromCenter_pix	|      |       |             |
|kKeepAliveEyeDart_MaxDistFromCenterFocused_pix	|      |       |             |
|kKeepAliveEyeDart_MediumDistanceThresh_pix	|      |       |             |
|kKeepAliveEyeDart_MediumShiftFraction	|      |       |             |
|kKeepAliveEyeDart_MediumSquashFraction	|      |       |             |
|kKeepAliveEyeDart_OuterEyeScaleIncrease	|      |       |             |
|kKeepAliveEyeDart_ShiftLagFraction	|      |       |             |
|kKeepAliveEyeDart_SpacingMaxTime_ms	|      |       |             |
|kKeepAliveEyeDart_SpacingMinTime_ms	|      |       |             |
|kKeepAliveEyeDart_UpMaxScale	|      |       |             |
|kMaxBlinkSpacingTimeForScreenProtection_ms	|      |       |             |

### Habitat console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kDevForceBeginConfirmHabitat|      |       |             |
|          |      |       |             |
|          |      |       |             |

### TrackingActions console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kOverride_PanDuration_s|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Face.ParameterizedFace console variables

### WallTime console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kProcFace_AntiAliasingFilter|      |       |             |
|kProcFace_AntiAliasingSigmaFraction|      |       |             |
|kProcFace_AntiAliasingSize|      |       |             |
|kProcFace_Display|      |       |             |
|kProcFace_EllipseDelta|      |       |             |
|kProcFace_EnableAntiAliasing|      |       |             |
|kProcFace_EyeLightnessMultiplier|      |       |             |
|kProcFace_Gamma|      |       |             |
|kProcFace_GammaType|      |       |             |
|kProcFace_HotspotFalloff|      |       |             |
|kProcFace_HotspotRender|      |       |             |
|kProcFace_InterpolationType|      |       |             |
|kProcFace_LineType|      |       |             |
|kProcFace_NoiseMaxLightness|      |       |             |
|kProcFace_NoiseMinLightness|      |       |             |
|kProcFace_NoiseNumFrames|      |       |             |
|kProcFace_NominalEyeSpacing|      |       |             |
|ProcFace_OverrideEyeParams|      |       |             |
|ProcFace_OverrideRightEyeParams|      |       |             |
|ProcFace_FromLinear|      |       |             |
|ProcFace_ToLinear|      |       |             |
|ProcFace_DefaultScanlineOpacity|      |       |             |
|ProcFace_NominalEyeSpacing|      |       |             |
|ProcFace_NoiseFraction|      |       |             |
|ProcFace_UseAntiAliasedLines|      |       |             |
|ProcFace_GlowRender|      |       |             |
|ProcFace_GlowSizeMultiplier|      |       |             |
|ProcFace_GlowLightnessMultiplier|      |       |             |
|ProcFace_GlowGaussianFilter|      |       |             |
|ProcFace_AntiAliasingGaussianFilter|      |       |             |



### Face.ScanlineDistortion console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kProcFaceScanline_MaxShiftNoise|      |       |             |
|kProcFaceScanline_OffNoiseMaxWidth|      |       |             |
|kProcFaceScanline_OffNoiseProb|      |       |             |

### FaceInfoScreenManager console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kAlexaNotificationTimeout_s|      |       |             |
|kButtonPressDurationForShutdown_ms|      |       |             |
|kFakeButtonPressType|      |       |             |
|kToggleMuteTimeout_s|      |       |             |

### GlitchLights console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kGlitchLightDelay_ms|      |       |             |
|kGlitchLightDuration_ms|      |       |             |
|          |      |       |             |

### HeldInPalm.Coordinator console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kMaxTimeForInitialHeldInPalmReaction_ms|      |       |             |
|          |      |       |             |
|          |      |       |             |

### kWebvizUpdatePeriod console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kWebvizUpdatePeriod|      |       |             |
|          |      |       |             |
|          |      |       |             |


### LiftLoadTest console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kNumLiftRaises|      |       |             |
|          |      |       |             |
|          |      |       |             |

### ManualAnimationPlayback console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kShouldDisplayKeyframeNumber|      |       |             |
|kNumberOfFramesToIncrement|      |       |             |
|          |      |       |             |

### MicData console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kBeatDetectorUseProcessedAudio|      |       |             |
|kDevForceProcessState|      |       |             |
|kMicData_ClipRecordTime_ms|      |       |             |
|kMicData_CollectRawTriggers|      |       |             |
|kMicData_ForceDisableMicDataProc|      |       |             |
|kMicData_ForceEnableMicDataProc|      |       |             |
|kMicData_QuietTimeCooldown_ms|      |       |             |
|kMicData_SaveRawFullIntent|      |       |             |
|kMicData_SaveRawFullIntent_WakeWordless|      |       |             |
|kMicData_SpeakerNoiseDisablesMics|      |       |             |
|kSaveNotches|      |       |             |

### Network console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kEnableVerboseNetworkLogging|      |       |             |
|kMaxPingTimesToTrackOverride|      |       |             |
|kPrintNetworkStats|      |       |             |
|kPrintNetworkStatsTimeSpacingMS|      |       |             |

### Network.Emulator console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|gUDPMaxLatency|      |       |             |
|gUDPMinLatency|      |       |             |
|gUDPNetEmulatorEnabled|      |       |             |
|gUDPNetEmulatorRuntimeToggling|      |       |             |
|gUDPRandomPacketLossPercentage|      |       |             |

### Network.Stats console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kLogMessageLatencyOnce|      |       |             |
|gNetStat1NumConnections|      |       |             |
|gNetStat2LatencyAvg|      |       |             |
|gNetStat3LatencySD|      |       |             |
|gNetStat4LatencyMin|      |       |             |
|gNetStat5LatencyMax|      |       |             |
|gNetStat6PingArrivedPC|      |       |             |
|gNetStat7ExtQueuedAvg_ms|      |       |             |
|gNetStat8ExtQueuedMin_ms|      |       |             |
|gNetStat9ExtQueuedMax_ms|      |       |             |
|gNetStatAQueuedAvg_ms|      |       |             |
|gNetStatBQueuedMin_ms|      |       |             |
|gNetStatCQueuedMax_ms|      |       |             |
|kNetConnStatsUpdate|      |       |             |

### OSState.DiskInfo console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kHighDiskPressureMultiple|      |       |             |
|kMediumDiskPressureMultiple|      |       |             |
|          |      |       |             |

### OSState.MemoryInfo console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kHighMemPressureMultiple|      |       |             |
|kMediumMemPressureMultiple|      |       |             |
|          |      |       |             |

### OSState.Temperature console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kFakeCpuTemperature_degC|      |       |             |
|kSendFakeCpuTemperature|      |       |             |
|          |      |       |             |

### OSState.Timezone console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kOSState_FakeNoTime|      |       |             |
|kOSState_FakeNoTimezone|      |       |             |
|          |      |       |             |

### OSState.WifiInfo console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kHighWifiErrorRate|      |       |             |
|kMediumWifiErrorRate|      |       |             |
|          |      |       |             |

### SpeechRecognizer console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kSuppressTriggerResponse|      |       |             |
|          |      |       |             |
|          |      |       |             |

### SpeechRecognizer.Alexa console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kAlexaRecognizerModel|      |       |             |
|kDefaultDetectThreshold|      |       |             |
|kForceRunNotchDetector|      |       |             |
|kSaveRawMicInput|      |       |             |

### SpeechRecognizer.AlexPlayback console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kAlexaPlaybackRecognizerModel|      |       |             |
|kPlaybackRecognizerSampleCountThreshold|      |       |             |
|          |      |       |             |

### SpeechRecognizer.Vector console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kVectorRecognizerModel|      |       |             |
|kVectorRecognizerModelSensitivity|      |       |             |
|          |      |       |             |

### StayOnCargerUntilCharged console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kSafeguardTimeout_s|      |       |             |
|          |      |       |             |
|          |      |       |             |

### TextToSpeech console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kEnablePausePrams|      |       |             |
|kLeadingSilence_ms|      |       |             |
|kMinPlayableFrames|      |       |             |
|kPauseBracket_ms|      |       |             |
|kPauseComma_ms|      |       |             |
|kPausePunctuation_ms|      |       |             |
|kPauseSemicolon_ms|      |       |             |
|kPauseSpelling_ms|      |       |             |
|kTrailingSilence_ms|      |       |             |
|kVoicePitch|      |       |             |
|kVoiceShaping|      |       |             |
|kVoiceSpeed|      |       |             |
|kWriteTTSFile|      |       |             |


### Vision.GazeDirection console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kFaceDirectedAtRobotMinXThres_mm|      |       |             |
|          |      |       |             |
|          |      |       |             |

### VoiceMessage console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kRequireKnownUser|      |       |             |
|          |      |       |             |
|          |      |       |             |

### WallTime console variables

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|kFakeWallTimeIsSynced|      |       |             |
|          |      |       |             |
|          |      |       |             |

### Not Yet Classified

| Variable | Type | Units | Description |
|----------|------|-------|-------------|
|          |      |       |             |
|          |      |       |             |
|          |      |       |             |
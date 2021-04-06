# Behaviour IDs

|Behavior ID|Description|
|-----------|-----------|
|AcknowledgeCharger||
|AcousticTestMode|This behavior is the first behavior called when Vector starts in an acousting testing mode|
|ActiveLookForFaces||
|AlexaSignInOut||
|Alexa ||
|AskForHelpOnSide||
|AskForHelp||
|Asleep ||
|BasicVoiceCommands||
|BeQuietAnims|This behavior is used to animate Vector going into a quiet state, and animate his eyes looking around.  See [quiet mode](quiet mode.md)|
|BeQuietLoop |This behavior is used to animate Vector's eyes looking around.  See [quiet mode](quiet mode.md)|
|BlackJackGoodLuckTTS||
|BlackJackHandleRTPResponses||
|BlackJackHitOrStandPrompt||
|BlackJackLookAtFaceInFront||
|BlackJackRequestToPlayAgain||
|BlackJackRequestToPlay||
|BlackJackTextToSpeech||
|BlackJackVoiceCommand||
|BlackJack||
|ChangeEyeColor||
|CheckForAndReactToHand||
|ClearChargerArea||
|ComeHereVoiceCommand||
|ConfirmCharger||
|ConfirmCube||
|ConfirmHabitat||
|ConnectToCube||
|CoordinateGlobalInterrupts||
|CoordinateInHabitat||
|CoordinateWhileHeldInPalm||
|CoordinateWhileInAir||
|CubeSpinnerConnectionGate||
|CubeSpinnerLookAroundInPlace||
|CubeTrickDispatcher||
|DanceBig||
|DanceForwardBackFlower||
|DanceFrontRightLeftPoint||
|DanceSTwoways||
|DanceSwell||
|DanceToTheBeatCoordinator||
|DanceToTheBeatVoiceCommand||
|DanceToTheBeat||
|DanceWiggleForwardWiggleBack||
|DefaultTextToSpeechLoop||
|DemoTimerUtilityCoordinator||
|DevBaseBehavior||
|DevBatteryLogging||
|DevCubeSpinnerConsole||
|DevCubeSpinner||
|DevDesignCubeLights||
|DevDisplayReadingsOnFace||
|DevEventSequenceCapture||
|DevImageCapture_PetsAndHands||
|DevImageCapture||
|DevPlannerTest||
|DevSquawkBoxTest||
|DevTestBlackjackViz||
|DevTestConnectToCube||
|DevTestPersonDetectorBehavior||
|DevTestPromptUser||
|DevTouchDataCollection||
|DevTurnInPlaceTest||
|DevViewCubeBackpackLights||
|DoATrickVoiceCommand||
|DockingTestSimple||
|DriveOffChargerCube||
|DriveOffChargerFace||
|DriveOffChargerIntoSocializing||
|DriveOffChargerRandomlyAnim||
|DriveOffChargerRandomly||
|DriveOffChargerStraight||
|EmergencyModeAnimDispatcher |This behavior gives a visual animation why Vector about the emergency mode.|
|EmergencyModeFindAndGoToHome|This specific behavior initiates the *FindAndGoToHome* behavior when in emergency mode.|
|EmergencyModeInAir  |This behavior animates a request to be picked up an placed in the dock when he has fallen or picked up.|
|EmergencyModeOffCharger |This behavior coordinates driving back to the charging dock|
|EmergencyModeTriggerWord|This animates a response to the trigger word, usually why it can't respond to commands right now.|
|EmergencyMode      |This behavior coordinates Vector driving to the charging dock, or requesting help.|
|ExploringBumpObject||
|ExploringExamineObstacle||
|ExploringGetIn||
|ExploringReferenceHuman||
|ExploringVoiceCommand||
|Exploring||
|FactoryCentroidExtractor||
|FetchCubeVoiceCommand||
|FetchCube||
|FindAndGoToHome||
|FindAndRequestHome||
|FindCubeAndPlayKeepaway||
|FindCubeAndThen||
|FindCube||
|FindFacesFetchCube||
|FindFacesPhoto||
|FindHomeForSleeping||
|FindHomeInHabitat||
|FindHome||
|FindYourCubeVoiceCommand||
|FistBumpVoiceCommand||
|FistBump||
|ForceStuckOnEdge||
|FrameFaces||
|GlobalInterruptions||
|GoHomeVoiceCommand||
|GoHome    ||
|GoToSleep ||
|GreetAfterLongTime ||
|HabitatMutedDispatcher||
|HabitatMutedVoiceCommandResponse||
|HeldInPalmDispatcher||
|HeldInPalmResponses ||
|HighLevelAI  ||
|HowOldAreYouCounting||
|HowOldAreYou ||
|InitNormalOperation|This behavior is the first behavior called when Vector starts normally.|
|InitPRDemo  |This behavior is the first behavior called when Vector starts in a PR demo mode.|
|InitialHeldInPalmReaction||
|InitialPickupAnimation ||
|IntentUnmatched ||
|InteractWithFaces||
|InteractWithStaticCube||
|InterruptingVoiceReactions||
|InvestigateCubeConnectionGate||
|InvestigateHeldCube ||
|KeepawayVoiceCommand||
|Keepaway ||
|KnowledgeGraphQuestion||
|KnowledgeGraphTTS||
|LeaveAMessage||
|LiftLoadTest ||
|ListenForBeatsLong||
|ListenForBeatsVoiceCommand||
|ListenForBeats||
|LookAtMeVoiceCommand||
|LookInPlaceHeadDownInAir||
|LookInPlaceHeadUpInAir||
|LookInPlaceHeadUp||
|LookOverThereVoiceCommand||
|MandatoryPhysicalReactions||
|MeetVictorAlreadyKnowYouPrompt||
|MeetVictor||
|MessagingPlaybackTTS||
|MessagingRecordTTS||
|ModeSelector  |Top level dispatcher; this is called by many different start up modes.  See [power management](power management.md) for a description.|
|MoveCube ||
|MovementBackward ||
|MovementForward  ||
|MovementTurnAround||
|MovementTurnLeft  ||
|MovementTurnRight ||
|NoCloud|The behavior is invoked when Vector can't reach the voice server; see [Communication trouble behaviors](communication trouble.md)|
|NoWifi |The behavior is invoked when Vector can't connect to a Wifi SSID; see [Communication trouble behaviors](communication trouble.md)|
|NormalWakeUp |This is called by [*InitNormalBehavior* on start](startup behavior.md).  It plays the wake up animation --- if it isn't night time, and this isn't a maintenance reboot.|
|NothingToDo_Idle||
|ObservingDriveOffCharger||
|ObservingEyeContact||
|ObservingFindFaces||
|ObservingLookAtFacesInAir||
|ObservingLookAtFaces||
|ObservingOffChargerHeadOnly||
|ObservingOnChargerEyeContact||
|ObservingOnChargerGetIn||
|ObservingOnChargerGetOut||
|ObservingOnChargerIdleAnim||
|ObservingOnChargerIdle||
|ObservingOnCharger||
|Observing||
|OnboardingComeHere||
|OnboardingEmulate1p0WaitForVC||
|OnboardingLookAtPhone||
|OnboardingLookAtUserOffCharger||
|OnboardingLookAtUserOnCharger||
|OnboardingLookAtUser||
|OnboardingPowerOff||
|OnboardingTeachComeHere||
|OnboardingTeachMeetVictor||
|OnboardingTeachWakeWord||
|OnboardingWakeUp||
|Onboarding |This behavior is the first behavior called when Vector starts "fresh" (new from factory or a clearing of user data) and is now onboarding a new human companion.|
|PRDemoBigGreeting||
|PRDemoComeHere||
|PRDemoExploring||
|PRDemoObserving||
|PRDemoSleeping||
|PRDemoStateMachine||
|PickUpCubeVoiceCommand||
|PickupCubeNoInitialReaction||
|PickupCube||
|PlaceCubeByCharger||
|PlayAGameVoiceCommand||
|PlayRollBlock||
|PlayWithCube||
|PlaybackMessage||
|PlaypenCameraCalibration||
|PlaypenDistanceSensor100mm||
|PlaypenDistanceSensor300mm||
|PlaypenDistanceSensor80mm||
|PlaypenDriftCheck||
|PlaypenDriveForwards||
|PlaypenEndChecks||
|PlaypenInitChecks||
|PlaypenMotorCalibration||
|PlaypenPickupCube||
|PlaypenSoundCheck||
|PlaypenTest ||
|PlaypenWaitToStart||
|PopAWheelieVoiceCommand||
|PopAWheelie ||
|PowerSaveStressTest||
|PowerSaveTest ||
|ProceduralTurnToMicDirection||
|PutDownBlockAtPose||
|PutDownBlock ||
|PutDownDispatch_LookForFaceAndCube||
|PuzzleMaze ||
|QuietModeEmergencyModeGoHome|This behavior coordinates driving back to the charging dock when the battery is low or overheated in quiet mode.  See [power managent](power management.md) for more details.|
|QuietMode   |The *QuietMode* behavior is when Vector's has been asked to be silent.  See [quiet mode](quiet mode.md)|
|ReactToAbuse ||
|ReactToAffirmative||
|ReactToApology ||
|ReactToBatteryTooHotToCharge||
|ReactToBody ||
|ReactToCliffDuringFetch||
|ReactToCliff ||
|ReactToDarkness ||
|ReactToFrustrationMajor||
|ReactToGazeDirectionSurface||
|ReactToGazeDirection||
|ReactToGoodBye ||
|ReactToGoodMorning||
|ReactToHand ||
|ReactToHello ||
|ReactToJoltInPalm||
|ReactToLove ||
|ReactToMotion ||
|ReactToMotorCalibration||
|ReactToNegative ||
|ReactToObstacle ||
|ReactToPalmTilt ||
|ReactToPickupFromPalm||
|ReactToPlacedOnSlope ||
|ReactToPutDownFromPalm||
|ReactToPutDown ||
|ReactToRobotOnBack||
|ReactToRobotOnFace||
|ReactToRobotOnSide||
|ReactToRobotShakenSnowGlobe||
|ReactToRobotShaken||
|ReactToSoundAsleep||
|ReactToSoundAwake ||
|ReactToSoundDirectionAsleep||
|ReactToSoundDirectionAwake ||
|ReactToTouchPetting||
|ReactToTriggerDirectionAwake ||
|ReactToUncalibratedHeadAndLift||
|ReactToUnclaimedIntent ||
|ReactToUnexpectedMovement||
|RequestHomeBecauseStuck||
|RequestToGoHome||
|ResetSafely||
|RespondToRenameFace||
|RollBlockIfNotVertical||
|RollCubeVoiceCommand||
|SDKDefault||
|SDKOverrideAll||
|SayName||
|SearchWithinBoundingBox||
|SeasonalHappyHolidays||
|SeasonalHappyNewYear||
|SelfTestButton||
|SelfTestDockWithCharger||
|SelfTestDriftCheck||
|SelfTestDriveForwards||
|SelfTestInitChecks||
|SelfTestLookAtCharger||
|SelfTestMotorCalibration||
|SelfTestPickup||
|SelfTestPutOnCharger2||
|SelfTestPutOnCharger||
|SelfTestScreenAndBackpack||
|SelfTestSoundCheck||
|SelfTestTouch||
|SelfTest||
|ShortLookAroundForFaceAndCube||
|ShowWallTime||
|ShutUpAnims|This behavior is used to animate Vector going into a quiet state (after beint told to shutup), and animate his eyes looking around.  See [quiet mode](quiet mode.md)|
|ShutUpMode |The *ShutUpMode* behavior is when Vector's has been asked to "shut up."  See [quiet mode](quiet mode.md)|
|SingletonAnticShowClock||
|SingletonCancelTimer||
|SingletonFindFaceInFrontWallTime||
|SingletonICantDoThat||
|SingletonPounceApproachWithProx||
|SingletonPounceDispatcher||
|SingletonPounceTurnLeft ||
|SingletonPounceTurnRight||
|SingletonPounceWithProx ||
|SingletonPoweringRobotOff|This behavior is active when Vector is powering down. See [power management](power management.md)|
|SingletonTimerAlreadySet||
|SingletonTimerAntic ||
|SingletonTimerCheckTime||
|SingletonTimerRinging ||
|SingletonTimerSet ||
|SingletonWallTimeCoordinator||
|SleepCycle  |This behavior is manages Vector going to sleep, playing and interacting. See [power management](power management.md)|
|SleepingPersonCheck||
|SleepingTriggerWord||
|SleepingWakeUpLights||
|SleepingWakeUp||
|SocializeGame||
|Socialize||
|StayOnChargerUntilCharged||
|StuckOnEdge||
|TakeAPhotoCoordinator||
|TestStackMonitors||
|TimerRingingPRDemo||
|TimerUtilityCoordinator||
|TrackCubeTest||
|TrackCube||
|TrackFaceTest||
|TrackingEyeContact||
|TriggerWordDetected||
|TriggerWordWithoutIntent||
|TurnToLastFace||
|UserDefinedBehaviorSelector||
|UserDefinedBehaviorTreeConfirmNewBehavior||
|UserDefinedBehaviorTreeRouter||
|UserDefinedBehaviorTreeTextToSpeech||
|VectorPlaysCubeSpinner||
|Volume||
|Wait||
|WeatherCloudyGeneric||
|WeatherColdClearGeneric||
|WeatherRainGeneric||
|WeatherResponses||
|WeatherSnowGeneric||
|WeatherStarsGeneric||
|WeatherSunnyGeneric||
|WeatherTextToSpeech||
|WeatherThunderstormsGeneric||
|WeatherWindyGeneric||
|WhatsMyNameVoiceCommand||
|WhileInAirDispatcher||
|WhileInAirResponsesPRDemo||
|WhileInAirResponses||
|WiggleBackOntoChargerFromPlatform||

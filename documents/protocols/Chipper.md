# The Chipper Services

This describes the interactions with Anki’s automatic speech response
server.  The audio after a "Hey Vector" is sent to servers for processing.
The servers send a response back, in the form of an intent.  This is a code and
a structure that represents an action to carry out in response to the spoken
request, query, or statement; it may represent the action requested, an answer
to a query, or an action that emotionally responds to what was said.  The
intent structures are described in another page.

## Common Elements

The enumerations and structures in this section are common to many commands.

### Enumerations
#### AudioEncoding
#### IntentService
#### LanguageCode
#### RobotMode

### Structures
The following structures are present in the Go code, but their use is not known.

#### Weather Location
The _WeatherLocation_ structure has the following fields:

_Table: JSON Parameters for the weather location structure_

|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_city_              | string   ||
|_country_           | string   ||
|_state_             | string   ||

## Commands and Responses
### Unknown
We see these in the logs, but it doesn’t match what the Go code has for generated grpc protobuf stuff…?

#### Request
The request sent to the server has the following fields

_Table: Parameters for ASR request_

|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_session_           | string   | Weirdo hex line thing|
|_type_              | string   | e.g. “streamOpen"|

Not sure where the stream open goes.  Does it upload the file, or live stream it?

#### Response
The server response message  has the following fields

_Table: Parameters for ASR response_

|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_intent_            | string	| The type of intent|
|_metadata_          | string	| This can be an empty string, but it can also be a string with colon delimited parameters.  It often has the pattern "text: unquoted-string  confidence: float handler: LEX"  The "text:" can be followed by transcription of the spoken text, the "confidence:" followed by a floating point number representing how confident the speech-to-text engine is in the transcription.|
|_parameters_        | JSON string|This is a string containing the JSON serialization of the intent parameters.|
|_type_              | string	  | e.g. "result"|

### Streaming Connection Check

#### Request

The _StreamingConnectionCheckRequest_ request message has the following fields:

_Table: JSON Parameters for the streaming connection check request_

|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_app_key_           |||		
|_audio_per_request_ |||
|_device_id_         | |Probably the robot's ESN.|
|_firmware_version_  |||	
|_input_audio_       |||
|_session_           |||
|_total_audio_ms_    |int||

#### Response
The _ConnectionCheckResponse_ response message has the following fields:

_Table: JSON Parameters for the connection check response_

|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_frames_received_   ||A count?|
|_status_            |_Status_||

### Streaming Intent
This is used to TBD on the server.

#### Request
The _StreamingIntentRequest_ request message has the following fields:

_Table: JSON Parameters for the streaming intent request_

|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_app_key_ |||
|_audio_encoding_    |_AudioEncoding_|Probably opus or ogg|
|_boot_id_ |||
|_device_id_         | |Probably the robot's ESN.|
|_firmware_version_ |||
|_input_audio_ |||
|_input_service_ |||
|_language_code_     |_LanguageCode_||
|_mode_              |_RobotMode_||
|_save_audio_        |bool||	
|_session_           |||
|_single_utterance_ |||
|_skip_das_         |bool||	
|_speech_only_      |bool||

#### Response
The _IntentResponse_ response message has the following fields:

_Table: JSON Parameters for the intent response_

|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_audio_id_          |||
|_device_id_         | |Probably the robot's ESN.|
|_intent_result_     |_IntentResult_||
|_is_final_          |bool||
|_mode_              |_RobotMode_||
|_session_|||
|_speech_result_     |_SpeechResult_||


The _IntentResult_ structure has the following fields:

_Table: JSON Parameters for the intent result structure_


|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_action_            |||		
|_all_parameters_present_|bool||
|_has_context_       |bool||
|_intent_confidence_ |float||
|_kgresponse_        |||	
|_parameters_        |||
|_query_text_        |||
|_service_           |||
|_speech_confidence_ |float||

The _SpeechResult_ structure has the following fields:

_Table: JSON Parameters for the speech result structure_


|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_is_final_          |bool	||
|_transcript_        |string||

### Streaming Knowledge Graph
This is used to query the knowledge graph on the server.
Note: I’m not convinced that Vector uses this.  It may be some of how the
server internally works that got left in Vector's _vic-cloud_.

#### Request
The _StreamingKnowledgeGraphRequest_ request message has the following fields:

_Table: JSON Parameters for the streaming knowledge graph request_

|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_app_key_           | ||
|_audio_encoding_    |_AudioEncoding_|Probably opus or ogg|
|_boot_id_           | ||
|_device_id_         | |Probably the robot's ESN.|
|_firmware_version_  | ||
|_input_audio_       | ||
|_language_code_     |_LanguageCode_||
|_save_audio_        | ||
|_skip_das_          |bool||
|_timezone_          | ||

#### Response
The _KnowledgeGraphResponse_ response message has the following fields:

_Table: JSON Parameters for the streaming knowledge graph response_


|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_audio_id_          | ||
|_command_type_      | ||
|_device_id_         | |Probably the robot's ESN.|
|_domains_used_      | ||
|_query_text_        | ||
|_session_           | ||
|_spoken_text_       | ||
|_text_input_        | ||


### Text

Note: I'm not convinced that Vector uses this.  It may be some of how the
server internally works that got left in Vector's vic-cloud.

#### Request
The _TextRequest_ request message has the following fields:

_Table: JSON Parameters for the text request_


|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_device_id_         | |Probably the robot's ESN.|
|_firmware_version_  | ||
|_intent_service_    |_IntentService_||
|_language_code_     |_LanguageCode_||
|_mode_              |_RobotMode_||
|_session_           |||
|_skip_das_          |bool||



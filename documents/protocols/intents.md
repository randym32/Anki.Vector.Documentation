# Intent Structures

This describes the structures associated with intents.
The audio after a "Hey Vector" is sent to servers for processing.
The servers send a response back, in the form of an intent.  This is a code and
a structure that represents an action to carry out in response to the spoken
request, query, or statement; it may represent the action requested, an answer
to a query, or an action that emotionally responds to what was said.

## Parameters for the Intents

The following are the parameters for each of the  intents.  These structures
are serialized as a JSON string and passed in the parameters property of the ASR
response.  The intents not listed below do not have any added parameters properties.

### Clock set timer

The _intent_clock_settimer_extend_ intent parameters structure has the following properties:

_Table: **intent_clock_settimer_extend** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_timer_duration_    | int      |seconds| number of seconds to set the timer to.|

### Global Delete

The _intent_global_delete_extend_ intent parameters structure has the following properties:

_Table: **intent_global_stop_deletable** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_entity_behavior_deletable_|string|See the table below for an enumeration of the allowed values.|The item to delete.|

The set of acceptable items that can be deleted include:

| String | Description|
|--------|------------|
|message ||
|photo   ||
|timer   ||

### Global stop
The _intent_global_stop_extend_ intent parameters structure has the following properties:

_Table: **intent_global_stop_extend** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_entity_behavior_stoppable_|string|See the table above for an enumeration of the allowed values.|The item to delete.|



### Imperative Eye Color
The _intent_imperative_eyecolor_extend_ intent parameters structure has the following properties:

_Table: **intent_imperative_eyecolor_extend** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_eye_color_         |string    | See the table below for an enumeration of the allowed values. |The name of the color to set the eye color to.  |

The enumeration of eye color values:

| String | Description|
|--------|------------|
|COLOR_BLUE| |
|COLOR_GREEN||
|COLOR_ORANGE||
|COLOR_PURPLE||
|COLOR_TEAL||
|COLOR_YELLOW||


### Imperative Volume Lvel

The _intent_imperative_volumelevel_extend_ intent parameters structure has the following properties:

_Table: **intent_imperative_volumelevel_extend** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_volume_level_      | string   |See the table below for an enumeration of the allowed values.|The name of the volume level to change to.|

The enumeration of volume levels:

| String | Description|
|--------|------------|
|VOLUME_1||
|VOLUME_2||
|VOLUME_3||
|VOLUME_4||
|VOLUME_5||


### Knowledge Response

This _intent_knowledge_response_extend_ intent parameters structure has the following properties:

_Table: **intent_knowledge_response_extend** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_answer_            | string   | The text to be spoken |
|_answer_type_       | string   | "InformationCommand" "NoResultCommand" |
|_query_text_        | string	| The text of the question asked. |


### Play Message

This _intent_message_playmessage_extend_ intent parameters structure has the following properties:

_Table: **intent_message_playmessage_extend** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_given_name_        | string   |       | The name of the person to send the message to. |

### User name

This _intent_names_username_extend_ intent parameters structure has the following properties:

_Table: **intent_names_username_extend** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_username_          | string   |       |The name of the user|

### Take Photo

The _intent_photo_take_extend_ intent parameters structure has the following properties:

_Table: **intent_photo_take_extend** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_entity_photo_selfie_|string   |       |Empty string if taking a photo, "photo_selfie" if taking a selfie.|

### Weather
The _intent_weather_extend_ intent parameters structure has the following properties:

_Table: **intent_weather_extend** properties_

|  Property          | Type     | Units | Description |
|--------------------|----------|-------|-------------|
|_condition_         | string	|	    |The current weather conditions.  One of "Clear", "Cloudy",  "Cold", "Rain", "Snow", "Stars", "Sunny", "Thunderstorms", or "Windy"|
|_is_forecast_       | string   |"false" or "true"|"false" if it is the current weather conditions; "true"  if forecasted weather conditions.|
|_local_datetime_    | string   |       |The local time (where the weather conditions apply) in UTC ISO 8601 format.|
|_speakable_location_string_|string|    |The location name that Vector could employ in his verbal description of the temperature.|
|_temperature_       | string   |degrees|The current or forecasted temperature, in the given units.|
|_temperature_unit_  | string   |		|F or C, for the units|



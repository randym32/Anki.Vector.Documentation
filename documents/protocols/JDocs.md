# The JDocs Services

The _Vic-Cloud_ services stores information on a "JDocs" server.  This unusual
name appears to be short for "JSON Documents."  This server allows Vector
to store settings and usage statistics.  This allows the settings and usage to
be viewed on a mobile device on a remote network.

The interactions are basic: store, read, and delete a JSON blob by an
identifier.  The description below  gives the JSON keys, value format.
It is implemented as gRPC/protobuf interaction over HTTP.

The commands include:

* An 'echo' command to check connectivity with the server.
* Reading and writing a document
* Deleting a document
* Viewing account documents

## Common Elements

The enumerations and structures in this section are common to many commands.

### Enumerations

#### Status

### Structures

#### JDoc
The JDoc structure has the following fields:

_Table: JSON structure_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_client_meta_|	string	 | Probably an empty string
|_doc_version_|	uint64	 | A number used to uniquely identify changes to the setting structure, and be able to tell which ones is the more recent settings.  Most often this is the number of times that the settings have been changed.|
|_fmt_version_|	uint64	 | The version number of the jdoc structure schema; this is always 1. |
|_json_doc_   |	string   | The jdoc structure serialized as a string. |


## Commands and Responses

### Delete Document

This is used to remove the document from the server.

#### Request
The _DeleteDocReq_ request message has the following fields:

_Table: JSON Parameters for delete document request_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_account_    | string	 | The account to delete the document from.|
|_doc_name_   | string	 | The name of the document to delete.|
|_thing_      | string	 | The thing id is a 'vic:' followed by the serial number|

#### Response
The _DeleteDocResp_ response message has the following fields:

_Table: JSON Parameters for the delete document response_

|  Field         | Type     | Description |
|----------------|----------|-------------|
|_latest_version_|	uint64	| The current version of the document in the repository.
|_status_        | string   | |

### Echo Test

#### Request

The _EchoReq_ request message has the following fields:

_Table: JSON Parameters for the echo request_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_data_		|||

#### Response

The _EchoResp_ response message has the following fields:

_Table: JSON Parameters for the echo response_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_data_	      || comment: I'm not sure this field is sent back|

### Read Documents

#### Request
The _ReadDocsReq_ request message has the following fields:

_Table: JSON Parameters for the read documents request_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_account_    | string   | The account to read from. |
|_items_      | _ReadDocsReq_Item_ []|	Array of the items requested. |
|_thing_      | string   | The thing id is a 'vic:' followed by the serial number. |

The _ReadDocsReq_Item_ structure has the following fields:

_Table: JSON Parameters for the read documents item_

|  Field         | Type     | Description |
|----------------|----------|-------------|
|_doc_name_      | string	|The name of the document to retrieve.|
|_my_doc_version_| UInt64	|The version to retrieve(?)|

#### Response
The _ReadDocsResp_ response message has the following fields:

_Table: JSON Parameters for the read documents response_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_items_      |_ReadDocsResp_item[]|	An array of the documents.|

The _ReadDocsResp_Item_ structure has the following fields:

_Table: JSON Parameters for the read document item response_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_doc_        | _JDoc_   | The document structure. |
|_status_     | _Status_ ||

### View Account Document
This command is used to retrieve a JSON blob on the server.  The request allows
personally identifying information to be included or omitted.

#### Request
The _ViewDocReq_ request message has the following fields:

_Table: JSON Parameters for view account document request_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_account_    | string   | The account to read from.|
|_json_doc_   | _JDoc_   | The document structure. {TODO: why is this here? this makes it seem like it doesn’t }  _Optional_|
|_doc_name_   | string   | The name of the document to view.  _Optional_|
|_thing_      | string   | The thing id is a ‘vic:’ followed by the serial number. _Optional_|

#### Response
The _ViewDocsResp_ response message has the following fields:

_Table: JSON Parameters for view account document response_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_docs_       | TBD[]    | The documents (?)|

### Write Document
This command is used to store a JSON blob on the server.

#### Request
The _WriteDocReq_ request message has the following fields:

_Table: JSON Parameters for write document request_

|  Field      | Type     | Description |
|-------------|----------|-------------|
|_account_    | string   | The account to write to.|
|_doc_        | _JDoc_   | The document structure.|
|_doc_name_   | string   | The name of the document to write.|
|_thing_      | string   | The thing id is a 'vic:' followed by the serial number.|

#### Response
The _WriteDocResp_ response message has the following fields:

_Table: JSON Parameters for write document response_

|  Field             | Type     | Description |
|--------------------|----------|-------------|
|_latest_doc_version_| UInt64   |The current version of the document in the repository.|
|_status_            | _Status_ ||



# The Token Manager

This describes the interactions with token manager.  This server allows Vector
to protect any-old application from connecting to it.  Instead it requires
proof that the application "knows" the users account name and password.
That proof is in the form of a token given to it and the application after
the application has authenticated with the token manager.

The commands include:

* Primary user management: associating a user or client, refreshing the association, and remove the association
* Revoking tokens; listing the revoked tokens
* Revoking a factory certificate


## Common Elments
The enumerations and structures in this section are common to many commands.

### Structures

#### StsToken
The _StsToken_ structure has the following fields:

_Table: Parameters for the STS token structure_

|  Field     | Type	  | Description |
|------------|--------|-------------|
|_access_key_id_    |||
|_expiration_       |||
|_secret_access_key_|||
|_session_token_    ||The token from the security token service for the session.|

#### TokenBundle
The _TokenBundle_ structure has the following fields:

_Table: Parameters for the token bundle structure_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_client_token_||	|
|_sts_token_   || The token from the security token service|
|_token_	   |||

#### TokenPage
The _TokenPage_ structure has the following fields:

_Table: Parameters for the token page structure_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_done_      |||		
|_last_key_  |||	
|_tokens_    |???[]||

## Commands and Responses

### Associate Primary User
This command is used to TBD?
See also the disassociate primary user and reassociate primary user commands

#### Request
The _AssociatePrimaryUserRequest_ request message has the following fields:

_Table: Parameters for the associate primary user request_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_app_id_		|||
|_client_name_ |||	
|_expiration_minutes_|||
|_generate_sts_token_|||
|_revoke_client_tokens_|||
|_session_certificate_|||
|_skip_client_token_ |||

#### Response

The _AssociatePrimaryUserResponse_ response message has the following fields:

_Table: Parameters for the associate primary user response_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_data_		|||

### Associate Secondary Client

This command is used to TBD?

#### Request
The _AssociateSecondaryClientRequest_ request message has the following fields:

_Table: Parameters for the associate secondary client request_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_app_id_		|||
|_client_name_|||	
|_user_session_|||	

#### Response
The _AssociateSecondaryClientResponse_ response message has the following fields:

_Table: Parameters for the associate secondary client response_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_data_		|||

### Disassociate Primary User
This command is used to TBD?
See also the associate primary user and reassociate primary user commands.

#### Request
The _DisassociatePrimaryUserRequest_ request message has no fields.

#### Response
The _DisassociatePrimaryUserResponse_ response message has no fields.

### List Revoked Tokens
This command is used to TBD?

#### Request
The _ListRevokedTokensRequest_ request message has the following fields:

_Table: Parameters for the list revoked tokens request_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_previous_key_|||

#### Response
The _ListRevokedTokensResponse_ response message has the following fields:

_Table: Parameters for the list revoked tokens response_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_data_|||

### Reassociate Primary User
This command is used to TBD?
See also the associate primary user and disassociate primary user commands.

#### Request
The _ReassociatePrimaryUserRequest_ request message has the following fields:

_Table: Parameters for the reassociate primary user request_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_app_id_ |||
|_client_name_ |||		
|_expiration_minutes_ |||
|_generate_sts_token_ |||
|_skip_client_token_ |||

#### Response
The _ReassociatePrimaryUserResponse_ response message has the following fields:

_Table: Parameters for the reassociate primary user response_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_data_ |||

### Refreshing a Token
This command is used to TBD?

#### Request
The RefreshTokenRequest request message has the following fields:

_Table: Parameters for the refresh token request_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_expiration_minutes_|||	
|_refresh_jwt_tokens_|||	
|_refresh_sts_tokens_|||

#### Response
The _RefreshTokenResponse_ response message has the following fields:

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_data_ |||


### Revoking a Factory Certificate

This command is used to TBD?

#### Request
The _RevokeFactoryCertificateRequest_ request message has the following fields:

_Table: Parameters for the revoke factory certificate request_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_certificate_id_|||
		

#### Response
The _RevokeFactoryCertificateResponse_ response message no fields/

### Revoking a Token
This command is used to TBD?

#### Request
The _RevokeTokensRequest_ request message has the following fields:

_Table: Parameters for the revoke tokens request_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_key_ |||
|_search_by_index_ |||

#### Response
The _RevokeTokensResponse_ response message has the following fields:

_Table: Parameters for the revoke tokens response_

|  Field    | Type	 | Description |
|-----------|--------|-------------|
|_tokens_revoked_| [] | A list of the tokens that have been revoked.| 


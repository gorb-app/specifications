POST /v1/login

---

Authenticates the user, and issues an access token for future requests.

---

## Request

No request parameters or request body.

---

### 200 response

|Name|Type|Description|
|-|-|-|
|identifier|string|User's gorb ID. One of identifier and email **must** be implemented|
|email|string|User's email. One of identifier and email **must** be implemented|
|password|string|**Required**: The user's password (we need to figure out how exactly we're hashing + salting it on the client)|
|device_name|string|Name to help the user identify the device in their session list|

```json
{
    "identifier": "radial_4740",
    "password": "9r89mhs4czu4",
    "device_name": "Laptop"
}
```

---

## Responses

|Status|Description|
|-|-|
|200|Authentication successful|
|400|The post request included poorly formated data|
|403|Part of the cridentials are invalid.|

---

### 200

|Name|Type|Description|
|-|-|-|
|access_token|string|**Required**: The access token that will be used for further authentication|
|user_id|string|**Required**: The full gorb ID for the account|
|expires_in|int|How many seconds until the token expires and is invalidated|

```json
{
    "access_token": "gwLhWXD9wrqL3DwxXZ0VHUeOjr8am1yO",
    "user_id": "@radial_4740:gorb.app",
    "expires_in": 2592000
}
```
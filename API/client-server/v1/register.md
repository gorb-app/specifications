POST /v1/register

---

Registers the user, and issues an access token for future requests.

---

## Request

|Name|Type|Description|
|-|-|-|
|identifier|string|**Required** User's desired ID|
|email|string|**Required** User's email|
|password|string|**Required**: The user's password (we need to figure out how exactly we're hashing + salting it on the client)|
|device_name|string|Name to help the user identify the device in their session list|

```json
{
    "identifier": "radial_4740",
    "email": "radial_4740@yahoo.com",
    "password": "9r89mhs4czu4",
    "device_name": "Laptop"
}
```

---

## Responses

|Status|Description|
|-|-|
|200|Registration successful|
|400|The post request included poorly formated data|
|401|Signups are disabled, gorb ID not available, email already in use, or password doesn't meet the minimum security requirements|

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

---

### 401

|Name|Type|Description|
|-|-|-|
|signups_enabled|bool|Does the server have signups enabled?| 
|gorb_id_valid|bool|Is the given gorb ID even valid?| 
|gorb_id_available|bool|Is the given gorb ID available?| 
|email_valid|bool|Is the given email valid?| 
|email_available|bool|Is the given email available?| 
|password_minimum_length|bool|Is the given password long enough?| 
|password_special_characters|bool|If enforced by the server, is there enough special characters in the password?| 
|password_letters|bool|If enforced by the server, is there enough letters in the password?| 
|password_numbers|bool|If enforced by the server, is there enough numbers in the password?| 

```json
{   
    "signups_enabled": true,
    "gorb_id_valid": true,
    "gorb_id_available": true,
    "email_valid": true,
    "email_available": false,
    "password_minimum_length": true,
    "password_special_characters": false,
    "password_letters": true,
    "password_numbers": true,
}
```
POST /v1/auth/register

---

Registers the user, and issues an access token for future requests.

---

## Request

| Name        | Type   | Description                                                                    |
| ----------- | ------ | ------------------------------------------------------------------------------ |
| identifier  | string | **Required** User's desired ID.                                                |
| email       | string | **Required** User's email.                                                     |
| password    | string | **Required**: The user's password in SHA3-384.                                 |
| device_name | string | **Required**: Name to help the user identify the device in their session list. |

```json
{
  "identifier": "radial_4740",
  "email": "radial_4740@yahoo.com",
  "password": "f324cbd421326a2abaedf6f395d1a51e189d4a71c755f531289e519f079b224664961e385afcc37da348bd859f34fd1c",
  "device_name": "Laptop"
}
```

---

## Responses

| Status | Description                                                                                                                    |
|--------|--------------------------------------------------------------------------------------------------------------------------------|
| 200    | Registration successful.                                                                                                       |
| 400    | The post request included poorly formated data.                                                                                |
| 403    | Signups are disabled, gorb ID not available, email already in use, or password doesn't meet the minimum security requirements. |
| 500    | An unhandled error occured.                                                                                                    |

---

### 200

| Name          | Type   | Description                                                                                                                                  |
| ------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| access_token  | string | **Required**: The access token that will be used for further authentication.                                                                 |
| refresh_token | string | The refresh token that will be used to refresh the access token. Required for avoiding users having to log in after access token expiration. |

```json
{
  "access_token": "85b2afece430e0e924f2d4277324c868",
  "refresh_token": "aeb343482fcee3a293e887f5dc840ea8b0fc6b54a26c2584a95a5bc91ff4a749"
}
```

---

### 403

| Name                        | Type | Description                                                                    |
| --------------------------- | ---- | ------------------------------------------------------------------------------ |
| signups_enabled             | bool | Does the server have signups enabled?                                          |
| gorb_id_valid               | bool | Is the given gorb ID even valid?                                               |
| gorb_id_available           | bool | Is the given gorb ID available?                                                |
| email_valid                 | bool | Is the given email valid?                                                      |
| email_available             | bool | Is the given email available?                                                  |
| password_hashed             | bool | Is the password hashed using SHA3-384?                                         |
| password_minimum_length     | bool | Is the given password long enough?                                             |
| password_special_characters | bool | If enforced by the server, is there enough special characters in the password? |
| password_letters            | bool | If enforced by the server, is there enough letters in the password?            |
| password_numbers            | bool | If enforced by the server, is there enough numbers in the password?            |

```json
{
  "signups_enabled": true,
  "gorb_id_valid": true,
  "gorb_id_available": true,
  "email_valid": true,
  "email_available": false,
  "password_hashed": true,
  "password_minimum_length": true,
  "password_special_characters": false,
  "password_letters": true,
  "password_numbers": true
}
```

---

### 500

| Name  | Type   | Description                      |
| ----- | ------ | -------------------------------- |
| error | string | The error the server encountered |

```json
{
  "error": "Something went wrong!",
}
```

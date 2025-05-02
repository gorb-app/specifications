POST /v1/auth/login

---

Authenticates the user, and issues an access token for future requests.

---

## Request

| Name        | Type   | Description                                                                    |
| ----------- | ------ | ------------------------------------------------------------------------------ |
| username    | string | **Required**: Can be the Gorb ID or email of the user trying to log in         |
| password    | string | **Required**: The user's password in SHA3-384.                                 |
| device_name | string | **Required**: Name to help the user identify the device in their session list. |

```json
{
  "user_id": "radial_4740",
  "password": "f324cbd421326a2abaedf6f395d1a51e189d4a71c755f531289e519f079b224664961e385afcc37da348bd859f34fd1c",
  "device_name": "Laptop"
}
```

---

## Responses

| Status | Description                                     |
|--------|-------------------------------------------------|
| 200    | Authentication successful.                      |
| 400    | The post request included poorly formated data. |
| 403    | Part of the cridentials are invalid.            |
| 500    | An unhandled error occured.                     |

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

### 500

| Name  | Type   | Description                      |
| ----- | ------ | -------------------------------- |
| error | string | The error the server encountered |

```json
{
  "error": "Something went wrong!",
}
```

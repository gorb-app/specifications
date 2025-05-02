POST /v1/auth/refresh

---

Reauthenticates the user using the refresh token, and issues an access token for future requests.

---

## Request

| Name          | Type   | Description           |
| ------------- | ------ | --------------------- |
| refresh_token | string | User's refresh token. |

```json
{
  "refresh_token": "aeb343482fcee3a293e887f5dc840ea8b0fc6b54a26c2584a95a5bc91ff4a749",
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

| Name          | Type   | Description                                                                                                                                                                                                                                |
| ------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| access_token  | string | **Required**: The access token that will be used for further authentication.                                                                                                                                                               |
| refresh_token | string | The refresh token that will be used to refresh the access token. Required for avoiding users having to log in after access token expiration. NOTE: This endpoint returns the same refresh_token if it was generated less than 23 days ago. |

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

POST /v1/auth/revoke

---

Revokes authenticated refresh/access tokens owned by the user.

---

## Request

| Name         | Type   | Description                                                                                                 |
| ------------ | ------ | ----------------------------------------------------------------------------------------------------------- |
| access_token | string | User's access token to validate the session.                                                                |
| password     | string | SHA3-384 of user password to ensure its the user trying to do this and not someone who has the access token |
| device_name  | string | device_name that should be removed from the list of logins (NOTE: Removes all devices with the same name)   |

```json
{
  "access_token": "85b2afece430e0e924f2d4277324c868",
  "password": "f324cbd421326a2abaedf6f395d1a51e189d4a71c755f531289e519f079b224664961e385afcc37da348bd859f34fd1c",
  "device_name": "Laptop"
}
```

---

## Responses

| Status | Description                                     |
|--------|-------------------------------------------------|
| 200    | Deletion successful.                            |
| 400    | The post request included poorly formated data. |
| 403    | Part of the cridentials are invalid.            |
| 500    | An unhandled error occured.                     |

---

### 200

| Name    | Type | Description                                                           |
| ------- | ---- | --------------------------------------------------------------------- |
| deleted | bool | Returns true if the refresh/access token(s) were successfully deleted |

```json
{
  "deleted": true
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

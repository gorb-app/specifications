POST /v1/user/me
POST /v1/user/{UUID}

---

Gathers information about the requested user.

---

## Request

| Name         | Type   | Description                          |
| ------------ | ------ | ------------------------------------ |
| access_token | string | **Required**: The user's auth token. |


```json
{
    "access_token": "85b2afece430e0e924f2d4277324c868",
}
```

---

## Responses

| Status | Description                                     |
| ------ | ----------------------------------------------- |
| 200    | User data found.                                |
| 400    | The post request included poorly formated data. |
| 403    | Invalid access token.                           |
| 500    | An unhandled error occured.                     |

---

### 200

| Name         | Type   | Description                        |
| ------------ | ------ | ---------------------------------- |
| uuid         | string | UUID of the requested user         |
| username     | string | Username of the requested user     |
| display_name | string | Display Name of the requested user |

```json
{
  "uuid": "7292d678-e718-4dbc-b2d5-e42a22abfdd6",
  "username": "radial_4740",
  "display_name": "Radial"
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

POST /v1/login

---

Authenticates the user, and issues an access token for future requests.

---

## Request

| Name        | Type   | Description                                                                                                    |
|-------------|--------|----------------------------------------------------------------------------------------------------------------|
| identifier  | string | User's gorb ID. One of identifier and email **must** be implemented                                            |
| email       | string | User's email. One of identifier and email **must** be implemented                                              |
| password    | string | **Required**: The user's password (we need to figure out how exactly we're hashing + salting it on the client) |
| device_name | string | Name to help the user identify the device in their session list                                                |

```json
{
  "identifier": "radial_4740",
  "password": "9r89mhs4czu4",
  "device_name": "Laptop"
}
```

---

## Responses

| Status | Description                                    |
|--------|------------------------------------------------|
| 200    | Authentication successful                      |
| 400    | The post request included poorly formated data |
| 403    | Part of the cridentials are invalid.           |

---

### 200

| Name         | Type   | Description                                                                 |
|--------------|--------|-----------------------------------------------------------------------------|
| access_token | string | **Required**: The access token that will be used for further authentication |
| user_id      | string | **Required**: The full gorb ID for the account                              |
| expires_in   | int    | How many seconds until the token expires and is invalidated                 |

```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJAcmFkaWFsXzQ3NDA6Z29yYi5hcHAiLCJpZGVudGlmaWVyIjoicmFkaWFsXzQ3NDAiLCJpYXQiOjE3NDM4ODgyNDAsImV4cCI6MTc0NTk2MTg0MH0.MZsOfeOm98K2sgtJ3hIDy0iyX27tDJRgW5iSayBJIDM",
  "user_id": "@radial_4740:gorb.app",
  "expires_in": 86400,
  "refresh_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJAcmFkaWFsXzQ3NDA6Z29yYi5hcHAiLCJpZGVudGlmaWVyIjoicmFkaWFsXzQ3NDAiLCJpYXQiOjE3NDM4ODgyNDAsImV4cCI6MTc0NjQ4MDI0MH0.OvUDelrhELNBhizvAj7wm13YpDLYluI4sPeBmT5sPUg"
}
```

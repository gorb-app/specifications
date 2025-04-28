POST /v1/friend-request

---

Sends a friend request to the given user.

---

## Request

| Name         | Type   | Description                                                                                   |
|--------------|--------|-----------------------------------------------------------------------------------------------|
| access_token | string | **Required**: The user's auth token                                                           |
| identifier   | string | **Required**: The gorb ID of the user they want to friend                                     |
| message      | string | A message to send along with the friend request, for example to find to tell them who you are |

```json
{
    "access_token": "gwLhWXD9wrqL3DwxXZ0VHUeOjr8am1yO",
    "identifier": "@radial_4740:gorb.app",
    "message": "Heyo, Kira here"
}
```

---

## Responses

| Status | Description                                                                  |
|--------|------------------------------------------------------------------------------|
| 200    | Friend request sucessfully sent                                              |
| 400    | The post request included poorly formated data                               |
| 401    | The recipient is not accepting friend requests from the sender at the moment |
| 403    | Invalid access token                                                         |
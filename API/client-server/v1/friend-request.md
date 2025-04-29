POST /v1/friend-request

---

Sends a friend request to the given user. Friend requests can be accepted by having the given user send a friend request back.

---

## Request

| Name         | Type   | Description                                                                                    |
|--------------|--------|------------------------------------------------------------------------------------------------|
| access_token | string | **Required**: The user's auth token.                                                           |
| uuid         | string | **Required**: The UUID of the user they want to befriend.                                      |
| server       | string | The instance that user is on, can be left out if it's a local friend request.                  |
| message      | string | A message to send along with the friend request, for example to find to tell them who you are. |

```json
{
    "access_token": "gwLhWXD9wrqL3DwxXZ0VHUeOjr8am1yO",
    "uuid": "dcb445f1-16e7-4cd9-ac19-af07acaeb865",
    "server": "gorb.app",
    "message": "Heyo, Kira here"
}
```

---

## Responses

| Status | Description                                                                   |
|--------|-------------------------------------------------------------------------------|
| 200    | Friend request sucessfully sent.                                              |
| 400    | The post request included poorly formated data.                               |
| 401    | The recipient is not accepting friend requests from the sender at the moment. |
| 403    | Invalid access token.                                                         |
| 500    | An unhandled error occured.                                                   |
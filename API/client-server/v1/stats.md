GET /v1/stats

---

## Request

No request parameters or request body.

---

## Responses

| Status | Description                      |
| ------ | -------------------------------- |
| 200    | The current stats of the server. |

### 200 response

| Name         | Type   | Description                                                                                 |
| ------------ | ------ | ------------------------------------------------------------------------------------------- |
| accounts     | int    | The number of signed up accounts.                                                           |
| uptime       | int    | How many seconds the server has been running.                                               |
| version      | string | The current server version.                                                                 |
| build_number | string | The hash of the last commit in the git repo? (maybe we want to define this some other way). |

```json
{
    "accounts": 27,
    "uptime": 189275,
    "version": "0.0.2",
    "build_number": "1fa926dd05"
}
```
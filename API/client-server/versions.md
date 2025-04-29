GET /versions

---

## Request

No request parameters or request body.

---

## Responses

| Status | Description                           |
| ------ | ------------------------------------- |
| 200    | The versions supported by the server. |

### 200 response

| Name                 | Type                | Description                                                                                                           |
| -------------------- | ------------------- | --------------------------------------------------------------------------------------------------------------------- |
| unstable_features    | dict[string:bool]   | Unstable features that are supported by the server. Features not listed here indicate that a feature isn't supported. |
| versions             | list[string]        | **Required**: The supported protocol versions.                                                                        |

```json
{
    "unstable_features": {
        "example.feature": true
    },
    "versions": [
        "2",
        "3",
        "4",
    ]
}
```
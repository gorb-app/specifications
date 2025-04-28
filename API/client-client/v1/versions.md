GET /v1/versions

---

## Request

No request parameters or request body.

---

## Responses

|Status|Description|
|-|-|
|200|The versions supported by the client|

### 200 response

|Name|Type|Description|
|-|-|-|
|unstable_features|string:bool|**Required**: Unstable features that are supported by the client. Features not listed here indicate that a feature isn't supported.|
|versions|[string]|**Required**: The supported protocol versions

```json
{
    "unstable_features": {
        "example.feature": true
    },
    "versions": [
        "0.0.2",
        "1",
    ]
}
```
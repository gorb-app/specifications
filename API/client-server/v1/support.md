GET /v1/support

---

## Request

No request parameters or request body.

---

## Responses

| Status | Description                                    |
|--------|------------------------------------------------|
| 200    | Support information for the server             |
| 404    | No contact information has been made available |

### 200 response

| Name         | Type          | Description                              |
|--------------|---------------|------------------------------------------|
| contacts     | list[Contact] | A list of server administators           |
| support_page | string        | The URL of a webpage that may help users |

#### Contact
| Name          | Type   | Description                                                |
|---------------|--------|------------------------------------------------------------|
| email_address | string | Email address for the administrator                        |
| gorb_id       | string | The gorb ID for the administrator                          |
| role          | string | **Required**: A simple description of this responsible for |

```json
{
    "contacts": [
        {
            "email_address": "admin@gorbatron.org",
            "role": "Main Administrator"
        },
        {
            "email_address": "moderator@gorbatron.org",
            "gorb_id": "@moderator:gorbatron.org",
            "role": "Content Moderator"
        }
    ],
    "support_page": "https://help.gorb.app"
}
```
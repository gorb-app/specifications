#### <b><span style="color: lightgreen;">GET</span> <code>/v1/users</code></b>
Retrieves all [users](../../../models/User#user-object) in the [Instance](../../../models/Instance.md#instance-object).
##### Request
###### Optional Query Paramters

| Parameter    | Type            | Description                                                                    |
| ------------ | --------------- | ------------------------------------------------------------------------------ |
| limit        | integer         | Maximum amount of results returned, default is `100`                           |
| sort         | string          | Property to sort by, default is `uuid`                                         |
| order        | "asc" \| "desc" | Order in which results are returned, can be `asc` or `desc`, default is `desc` |
| username     | string          | Returns users with usernames that match the string the closest                 |
| display_name | string          | Returns users with display names that match the string the closest             |
| fields       | string          | Comma-separate list of fields to return                                        |
**Example Request**
`GET /v1/users?limit=10&sort=created_at&order=asc&fields=username,created_at`
##### Responses

| Status | Type                                                      | Description                                      |
| ------ | --------------------------------------------------------- | ------------------------------------------------ |
| 200    | array of [User](../../../models/User#user-object) objects | The request succeeded and an array is returned.  |
| 400    |                                                           | The post request included poorly formatted data. |
| 401    |                                                           | User is not authenticated.                       |
| 403    |                                                           | User does not have permission to list users.     |
| 500    |                                                           | An unhandled error occurred.                     |

###### 200
Returns an array of [User](../../../models/User#user-object) objects.

**Example Response**

```json
[
	{
		"uuid": "7b483ca9-031d-4061-a3a7-7d0f0a71df78",
		"username": "radical",
		"display_name": "Radical",
		"created_at": 1746203203713
	},
	{
		"uuid": "fd972804-6bd0-4787-9e84-59e2a245039a",
		"username": "sauceyred",
		"display_name": "SauceyRed",
		"created_at": 1746203284508
	}
]
```
#### <b><span style="color: lightgreen;">GET</span> <code>/v1/users/me</code></b>
Retrieves currently logged-in [user](../../../models/User#user-object) in the [Instance](../../../models/Instance.md#instance-object).
##### Responses

| Status | Type                                            | Description                                      |
| ------ | ----------------------------------------------- | ------------------------------------------------ |
| 200    | [User](../../../models/User#user-object) object | The request succeeded and the user is returned.  |
| 400    |                                                 | The post request included poorly formatted data. |
| 401    |                                                 | User is not authenticated.                       |
| 500    |                                                 | An unhandled error occurred.                     |

###### 200
Returns a [User](../../../models/User#user-object) object.

**Example Response**

```json
[
	{
		"uuid": "7b483ca9-031d-4061-a3a7-7d0f0a71df78",
		"username": "radical",
		"display_name": "Radical",
		"created_at": 1746203203713
	},
	{
		"uuid": "fd972804-6bd0-4787-9e84-59e2a245039a",
		"username": "sauceyred",
		"display_name": "SauceyRed",
		"created_at": 1746203284508
	}
]

## Message Object
Represents a message in a [[Channel]]/DM.

**Structure**

| Field       | Type                                                | Description                                     |
| ----------- | --------------------------------------------------- | ----------------------------------------------- |
| id          | string                                              | ID of the message                               |
| channel_id  | string                                              | ID of the channel the message was sent it       |
| author      | [[User]] object                                     | Author of the message                           |
| content     | string                                              | Content of the message                          |
| created_at  | timestamp                                           | When the message was sent                       |
| edited      | timestamp \| null                                   | When this message was edited, null if it hasn't |
| attachments | array of [[#Attachment Object\|Attachment]] objects | Files attached with the message, empty if none  |
| embeds      | array of [[#Embed Object\|Embed]] objects           | Embeds sent with the message, empty if none     |
**Example Message**
```json
{
	"id": "aa077418-c9e3-4703-bdd7-8187f230192c",
	"channel_id": "b61aebb9-0463-47cb-b007-c0940ada962b",
	"author": {
		"uuid": "26c8037c-2c35-4c0f-9504-35df82a1effc",
		"username": "sauceyred",
		"display_name": "💜The Sauce🔥",
		"created_at": "1746115074928"
	},
	"content": "heyo what's going on",
	"created_at": "1746110781000",
	"edited": null,
	"attachments": [],
	"embeds": []
}
```

## Embed Object
Represents an embed in a [[#Message Object|Message]].

**Structure**

| Field  | Type                                      | Description         |
| ------ | ----------------------------------------- | ------------------- |
| title  | string                                    | Title of the embed  |
| color  | integer                                   | Color of the embed  |
| fields | array of [[#Field Object\|Field]] objects | Fields of the embed |

**Example Embed**
```json
{
	"title": "SauceyRed's Profile",
	"color": 6572758,
	"fields": [
		{ "name": "Username", value: "sauceyred" },
		{ "name": "Height", value: "159" },
		{ "name": "" }
	]
}
```
### Field Object
Represents a field in an [[#Embed Object|Embed]].
**Structure**

| Field  | Type    | Description                                           |
| ------ | ------- | ----------------------------------------------------- |
| name   | string  | Name of the field                                     |
| value  | string  | Value of the field                                    |
| inline | boolean | Whether field is displayed inline, default is `false` |
**Example Field**
```json
{
	"name": "Username",
	"value": "sauceyred"
}
```
## Attachment Object
Represents an attachment in a [[#Message Object|Message]].

**Structure**

| Field | Type | Description |
| ----- | ---- | ----------- |
|       |      |             |

**Example Attachment**
```json
{
	"": ""
}
```
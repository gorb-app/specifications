## Guild Object
Represents a guild in an [Instance](Instance.md).

**Structure**

| Field        | Type                                            | Description                    |
| ------------ | ----------------------------------------------- | ------------------------------ |
| id           | string                                          | ID of the guild                |
| description  | string                                          | Description of the guild       |
| name         | string                                          | Name of the guild              |
| icon         | string                                          | URL for the icon               |
| owner_id     | string                                          | ID of the owner                |
| roles        | array of [Role](Role.md#role-object) objects    | Roles in the guild             |
| emojis       | array of [Emoji](Emoji.md#emoji-object) objects | Emojis in the guild            |
| member_count | integer                                         | Number of members in the guild |

### Role Object
**Structure**

| Field | Type   | Description             |
| ----- | ------ | ----------------------- |
| id    | string | ID of the role          |
| name  | string | Name of the role        |
| icon  | string | URL for the role's icon |


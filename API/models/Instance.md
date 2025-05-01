# We will probably have/need this right?
## Message Object
Represents a Gorb instance.

**Structure**

| Field        | Type                                           | Description                                           |
| ------------ | ---------------------------------------------- | ----------------------------------------------------- |
| id           | string                                         | ID of the instance                                    |
| name         | string                                         | Name of the instance                                  |
| accounts     | integer                                        | Number of accounts registered on the instance         |
| uptime       | integer                                        | Seconds since the instance was last started           |
| version      | string                                         | The version of Gorb that the instance is running      |
| build_number | string                                         | The build number of Gorb that the instance is running |
| guilds       | array of [[Guild#Guild Object\|Guild]] objects | Guilds in the instance                                |

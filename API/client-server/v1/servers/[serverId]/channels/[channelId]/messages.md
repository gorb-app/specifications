#### <b><span style="color: lightgreen;">GET</span> <code>/v1/servers/{serverId}/channels/{channelId}/messages</code></b>
Retrieves all [[Message|messages]] in a [[Guild]].
##### Responses

| Status | Description                                               |
| ------ | --------------------------------------------------------- |
| 200    | The request succeeded and the message object is returned. |
| 400    | The post request included poorly formated data.           |
| 401    | User is not authenticated.                                |
| 403    | User does not have permission to view the message.        |
| 500    | An unhandled error occurred.                              |

###### 200
Returns a [[Message]] object.
#### <b><span style="color: lightgreen;">GET</span> <code>/v1/servers/{serverId}/channels/{channelId}/messages/{messageId}</code></b>
Retrieves a [[Message]] from a channel.
##### Responses

| Status | Description                                               |
| ------ | --------------------------------------------------------- |
| 200    | The request succeeded and the message object is returned. |
| 400    | The post request included poorly formated data.           |
| 401    | User is not authenticated.                                |
| 403    | User does not have permission to view the message.        |
| 500    | An unhandled error occurred.                              |

###### 200
Returns a [[Message]] object.
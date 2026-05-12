
# Email Notification Callback

*This model accepts additional fields of type unknown.*

## Structure

`EmailNotificationCallback`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `messageId` | `string \| undefined` | Optional | - |
| `recipientEmail` | `string \| undefined` | Optional | - |
| `status` | [`Status1 \| undefined`](../../doc/models/status-1.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "messageId": "msg_001",
  "recipientEmail": "user@example.com",
  "status": "sent",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


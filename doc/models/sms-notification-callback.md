
# Sms Notification Callback

*This model accepts additional fields of type unknown.*

## Structure

`SmsNotificationCallback`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `messageId` | `string \| undefined` | Optional | - |
| `phoneNumber` | `string \| undefined` | Optional | - |
| `status` | [`Status2 \| undefined`](../../doc/models/status-2.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "messageId": "sms_002",
  "phoneNumber": "+15551234567",
  "status": "delivered",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# Notification Callback

*This model accepts additional fields of type unknown.*

## Structure

`NotificationCallback`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `notificationType` | `string` | Required | - |
| `subject` | `string` | Required | - |
| `message` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "notificationType": "email",
  "subject": "Order Coonfirmation",
  "message": "msg_email_789",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


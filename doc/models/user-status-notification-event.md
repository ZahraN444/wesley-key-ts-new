
# User Status Notification Event

*This model accepts additional fields of type unknown.*

## Structure

`UserStatusNotificationEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `userStatusNotificationEventType` | `string` | Required, Constant | **Value**: `'user.status'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "userStatusNotificationEventType": "user.status",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# User Action Notification Event

*This model accepts additional fields of type unknown.*

## Structure

`UserActionNotificationEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `userActionNotificationEventType` | `string` | Required, Constant | **Value**: `'user.action'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "userActionNotificationEventType": "user.action",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


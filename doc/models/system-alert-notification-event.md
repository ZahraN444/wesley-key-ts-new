
# System Alert Notification Event

*This model accepts additional fields of type unknown.*

## Structure

`SystemAlertNotificationEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `systemAlertNotificationEventType` | `string` | Required, Constant | **Value**: `'system.alert'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "systemAlertNotificationEventType": "system.alert",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


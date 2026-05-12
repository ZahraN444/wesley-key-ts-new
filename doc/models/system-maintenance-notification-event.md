
# System Maintenance Notification Event

*This model accepts additional fields of type unknown.*

## Structure

`SystemMaintenanceNotificationEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `systemMaintenanceNotificationEventType` | `string` | Required, Constant | **Value**: `'system.maintenance'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "systemMaintenanceNotificationEventType": "system.maintenance",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


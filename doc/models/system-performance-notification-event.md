
# System Performance Notification Event

*This model accepts additional fields of type unknown.*

## Structure

`SystemPerformanceNotificationEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `systemPerformanceNotificationEventType` | `string` | Required, Constant | **Value**: `'system.performance'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "systemPerformanceNotificationEventType": "system.performance",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# User Preference Notification Event

*This model accepts additional fields of type unknown.*

## Structure

`UserPreferenceNotificationEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `userPreferenceNotificationEventType` | `string` | Required, Constant | **Value**: `'user.preference'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "userPreferenceNotificationEventType": "user.preference",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


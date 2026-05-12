
# Audit Log Event

*This model accepts additional fields of type unknown.*

## Structure

`AuditLogEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `eventType` | [`EventType3 \| undefined`](../../doc/models/event-type-3.md) | Optional | - |
| `actor` | `string \| undefined` | Optional | - |
| `action` | `string \| undefined` | Optional | - |
| `context` | `unknown \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "eventType": "audit.log",
  "actor": "actor0",
  "action": "action2",
  "context": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


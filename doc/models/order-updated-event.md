
# Order Updated Event

*This model accepts additional fields of type unknown.*

## Structure

`OrderUpdatedEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `eventType` | [`EventType \| undefined`](../../doc/models/event-type.md) | Optional | - |
| `orderUpdatedId` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "orderUpdatedId": 91,
  "eventType": "order.updated",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


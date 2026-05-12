
# Primitive Collection Event

*This model accepts additional fields of type unknown.*

## Structure

`PrimitiveCollectionEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `eventType` | [`EventType2 \| undefined`](../../doc/models/event-type-2.md) | Optional | - |
| `ids` | `number[]` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "eventType": "primitive.variant",
  "ids": [
    77,
    78,
    79
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


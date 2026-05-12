
# Payment Completed Event

*This model accepts additional fields of type unknown.*

## Structure

`PaymentCompletedEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `eventType` | [`EventType1 \| undefined`](../../doc/models/event-type-1.md) | Optional | - |
| `paymentId` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "paymentId": 91,
  "eventType": "payment.completed",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


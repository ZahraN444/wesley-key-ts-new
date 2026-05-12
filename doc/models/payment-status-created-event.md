
# Payment Status Created Event

*This model accepts additional fields of type unknown.*

## Structure

`PaymentStatusCreatedEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentStatusCreatedId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "paymentStatusCreatedId": "ps_123",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


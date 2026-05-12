
# Payment Status Updated Event

*This model accepts additional fields of type unknown.*

## Structure

`PaymentStatusUpdatedEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `paymentStatusId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "paymentStatusId": "ps_123",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


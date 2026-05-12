
# Payment Callback

*This model accepts additional fields of type unknown.*

## Structure

`PaymentCallback`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `string` | Required | - |
| `paymentStatus` | [`PaymentStatus`](../../doc/models/payment-status.md) | Required | - |
| `transactionId` | `string` | Required | - |
| `amount` | `number \| undefined` | Optional | - |
| `currency` | `string \| undefined` | Optional | - |
| `timestamp` | `string \| undefined` | Optional | - |
| `failureReason` | `string \| undefined` | Optional | Reason for payment failure (if applicable) |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "orderId": "order_789",
  "paymentStatus": "success",
  "transactionId": "txn_abc123",
  "amount": 59.98,
  "currency": "USD",
  "timestamp": "09/19/2025 10:35:00",
  "failureReason": "failureReason0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


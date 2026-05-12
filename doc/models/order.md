
# Order

*This model accepts additional fields of type unknown.*

## Structure

`Order`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `string \| undefined` | Optional | - |
| `customerId` | `string \| undefined` | Optional | - |
| `items` | [`OrderItem[] \| undefined`](../../doc/models/order-item.md) | Optional | - |
| `totalAmount` | `number \| undefined` | Optional | - |
| `status` | [`Status \| undefined`](../../doc/models/status.md) | Optional | - |
| `createdAt` | `string \| undefined` | Optional | - |
| `updatedAt` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "orderId": "order_789",
  "customerId": "cust_12345",
  "totalAmount": 59.98,
  "status": "pending",
  "createdAt": "09/19/2025 10:30:00",
  "updatedAt": "09/19/2025 10:30:00",
  "items": [
    {
      "productId": "productId2",
      "quantity": 22,
      "price": 56.94,
      "description": "description2",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


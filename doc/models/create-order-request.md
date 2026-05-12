
# Create Order Request

*This model accepts additional fields of type unknown.*

## Structure

`CreateOrderRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `customerId` | `string` | Required | Unique identifier for the customer |
| `items` | [`OrderItem[]`](../../doc/models/order-item.md) | Required | **Constraints**: *Minimum Items*: `1` |
| `callbackUrl` | `string` | Required | URL to receive callback notifications |
| `document` | `string \| undefined` | Optional | Binary file upload |
| `metadata` | `unknown \| undefined` | Optional | Additional order metadata |
| `attributes` | `Record<string, string> \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "customerId": "cust_12345",
  "items": [
    {
      "productId": "prod_001",
      "quantity": 2,
      "price": 29.99,
      "description": "Premium Widget",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "callbackUrl": "https://merchant.example.com/callbacks/payment",
  "attributes": {
    "color": "red",
    "size": "XL"
  },
  "document": "document2",
  "metadata": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# Order Item

*This model accepts additional fields of type unknown.*

## Structure

`OrderItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `productId` | `string` | Required | - |
| `quantity` | `number` | Required | **Constraints**: `>= 1` |
| `price` | `number` | Required | **Constraints**: `>= 0` |
| `description` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
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
```


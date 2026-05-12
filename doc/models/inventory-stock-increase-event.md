
# Inventory Stock Increase Event

*This model accepts additional fields of type unknown.*

## Structure

`InventoryStockIncreaseEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `inventoryStockIncreaseEventType` | `string` | Required, Constant | **Value**: `'stock.increase'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "inventoryStockIncreaseEventType": "stock.increase",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


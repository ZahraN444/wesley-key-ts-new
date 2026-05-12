
# Inventory Stock Decrease Event

*This model accepts additional fields of type unknown.*

## Structure

`InventoryStockDecreaseEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `inventoryStockDecreaseEventType` | `string` | Required, Constant | **Value**: `'stock.decrease'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "inventoryStockDecreaseEventType": "stock.decrease",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


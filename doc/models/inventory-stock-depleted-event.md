
# Inventory Stock Depleted Event

*This model accepts additional fields of type unknown.*

## Structure

`InventoryStockDepletedEvent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `inventoryStockDepletedEventType` | `string` | Required, Constant | **Value**: `'stock.depleted'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "inventoryStockDepletedEventType": "stock.depleted",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```



# Inventory Change Event Body

## Class Name

`InventoryChangeEventBody`

## Cases

| Type |
|  --- |
| [`InventoryStockIncreaseEvent`](../../../doc/models/inventory-stock-increase-event.md) |
| [`InventoryStockDecreaseEvent`](../../../doc/models/inventory-stock-decrease-event.md) |
| [`InventoryStockDepletedEvent`](../../../doc/models/inventory-stock-depleted-event.md) |

## InventoryStockIncreaseEvent

### Initialization Code

#### Example

```ts
const value: InventoryChangeEventBody = {
  inventoryStockIncreaseEventType: 'stock.increase',
};
```

## InventoryStockDecreaseEvent

### Initialization Code

#### Example

```ts
const value: InventoryChangeEventBody = {
  inventoryStockDecreaseEventType: 'stock.decrease',
};
```

## InventoryStockDepletedEvent

### Initialization Code

#### Example

```ts
const value: InventoryChangeEventBody = {
  inventoryStockDepletedEventType: 'stock.depleted',
};
```


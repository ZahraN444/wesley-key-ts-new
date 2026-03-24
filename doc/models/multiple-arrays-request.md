
# Multiple Arrays Request

## Structure

`MultipleArraysRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `array1` | `string[]` | Required | An array containing items of type string |
| `array2` | `number[] \| undefined` | Optional | An array containing items of type integer |

## Example (as JSON)

```json
{
  "Array1": [
    "Array19",
    "Array10"
  ],
  "Array2": [
    99,
    98,
    97
  ]
}
```


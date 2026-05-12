
# Package

*This model accepts additional fields of type unknown.*

## Structure

`Package`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `packageId` | `string \| undefined` | Optional | - |
| `weight` | `number \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "packageId": "packageId0",
  "weight": 83.8,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


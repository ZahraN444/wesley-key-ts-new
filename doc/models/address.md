
# Address

*This model accepts additional fields of type unknown.*

## Structure

`Address`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `street` | `string` | Required | - |
| `city` | `string` | Required | - |
| `zip` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "street": "123 Main St",
  "city": "New York",
  "zip": "10001",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


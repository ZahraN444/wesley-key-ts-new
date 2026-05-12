
# Delivery Details

*This model accepts additional fields of type unknown.*

## Structure

`DeliveryDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `method` | `string \| undefined` | Optional | - |
| `eta` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "method": "method6",
  "eta": "2016-03-13T12:52:32.123Z",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


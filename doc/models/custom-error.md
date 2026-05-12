
# Custom Error

*This model accepts additional fields of type unknown.*

## Structure

`CustomError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | `string` | Required | Error code |
| `message` | `string` | Required | Human-readable error message |
| `details` | `unknown \| undefined` | Optional | Additional error details |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_request",
  "message": "The request body is invalid",
  "details": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


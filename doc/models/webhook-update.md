
# Webhook Update

*This model accepts additional fields of type unknown.*

## Structure

`WebhookUpdate`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `url` | `string \| undefined` | Optional | - |
| `events` | `string[] \| undefined` | Optional | - |
| `secret` | `string \| undefined` | Optional | - |
| `active` | `boolean \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "url": "url6",
  "events": [
    "events8",
    "events9"
  ],
  "secret": "secret2",
  "active": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


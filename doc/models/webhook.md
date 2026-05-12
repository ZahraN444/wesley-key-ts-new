
# Webhook

*This model accepts additional fields of type unknown.*

## Structure

`Webhook`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `webhookId` | `string \| undefined` | Optional | - |
| `createdAt` | `string \| undefined` | Optional | - |
| `updatedAt` | `string \| undefined` | Optional | - |
| `lastDelivery` | `string \| undefined` | Optional | Timestamp of the last successful delivery |
| `deliveryCount` | `number \| undefined` | Optional | Total number of events delivered |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "webhookId": "webhook_456",
  "createdAt": "09/19/2025 09:00:00",
  "updatedAt": "09/19/2025 09:00:00",
  "deliveryCount": 42,
  "lastDelivery": "2016-03-13T12:52:32.123Z",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


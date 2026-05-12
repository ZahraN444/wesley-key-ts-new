
# Webhook Registration

*This model accepts additional fields of type unknown.*

## Structure

`WebhookRegistration`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `url` | `string` | Required | The endpoint URL that will receive webhook events |
| `events` | [`Event[]`](../../doc/models/event.md) | Required | List of events to subscribe to |
| `secret` | `string \| undefined` | Optional | Secret key for webhook signature verification |
| `active` | `boolean \| undefined` | Optional | Whether the webhook is active<br><br>**Default**: `true` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "url": "https://merchant.example.com/webhooks/events",
  "events": [
    "order.created",
    "payment.completed"
  ],
  "secret": "webhook_secret_key_123",
  "active": true,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```


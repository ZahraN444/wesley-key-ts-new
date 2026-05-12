## Webhooks B Handler

Multi-event webhook group with oneOf payload structures. Uses a message template that also includes a request header pointer.

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Webhook-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [userNotificationEvent](../../../doc/events/webhooks/webhooks_b/user-notification-event.md) | Triggered when user-related notifications occur |
| [systemNotificationEvent](../../../doc/events/webhooks/webhooks_b/system-notification-event.md) | Triggered when system-wide notifications occur |
| [inventoryChangeEvent](../../../doc/events/webhooks/webhooks_b/inventory-change-event.md) | Triggered when inventory stock levels change |

## SDK Usage Example

```ts
import express, { Request, Response } from 'express';
import {
  convertExpressRequest,
  WebhooksBHandler,
  WebhooksBParsingResult,
} from 'package-wesley-key-ts-new';

const app = express();
app.use(express.json());

const handler = new WebhooksBHandler('hmac-secret-key');

app.post('/webhooks', (req: Request, res: Response) => {
  // Use the provided handler to verify and parse the incoming event
  const result = handler.verifyAndParseEvent(convertExpressRequest(req));

  if (WebhooksBParsingResult.isUserNotificationEventEvent(result)) {
    // Result narrowed down to type UserNotificationEvent
    res.status(200).send(result);
  } else if (WebhooksBParsingResult.isSystemNotificationEventEvent(result)) {
    // Result narrowed down to type SystemNotificationEvent
    res.status(200).send(result);
  } else if (WebhooksBParsingResult.isInventoryChangeEventEvent(result)) {
    // Result narrowed down to type InventoryChangeEvent
    res.status(200).send(result);
  } else if (WebhooksBParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
    res.status(400).send(result);
  } else if (WebhooksBParsingResult.isSignatureVerificationFailure(result)) {
    // Result narrowed down to type SignatureVerificationFailure
    res.status(400).send(result);
  }
});
```


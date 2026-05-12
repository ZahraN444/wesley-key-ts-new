## Webhooks A Handler

Advanced webhook group for payment status events

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [paymentStatusUpdated](../../../doc/events/webhooks/webhooks_a/payment-status-updated.md) | Triggered when a payment status is updated via POST method |
| [paymentStatusCreated](../../../doc/events/webhooks/webhooks_a/payment-status-created.md) | Triggered when a new payment status is created |

## SDK Usage Example

```ts
import express, { Request, Response } from 'express';
import {
  convertExpressRequest,
  WebhooksAHandler,
  WebhooksAParsingResult,
} from 'package-wesley-key-ts-new';

const app = express();
app.use(express.json());

const handler = new WebhooksAHandler('hmac-secret-key');

app.post('/webhooks', (req: Request, res: Response) => {
  // Use the provided handler to verify and parse the incoming event
  const result = handler.verifyAndParseEvent(convertExpressRequest(req));

  if (WebhooksAParsingResult.isPaymentStatusUpdatedEvent(result)) {
    // Result narrowed down to type PaymentStatusUpdated
    res.status(200).send(result);
  } else if (WebhooksAParsingResult.isPaymentStatusCreatedEvent(result)) {
    // Result narrowed down to type PaymentStatusCreated
    res.status(200).send(result);
  } else if (WebhooksAParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
    res.status(400).send(result);
  } else if (WebhooksAParsingResult.isSignatureVerificationFailure(result)) {
    // Result narrowed down to type SignatureVerificationFailure
    res.status(400).send(result);
  }
});
```


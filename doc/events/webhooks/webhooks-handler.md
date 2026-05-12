## Webhooks Handler

Standard webhook group for order and payment events

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [orderCreated new testing my newy tesingggggg toc hejcjk](../../../doc/events/webhooks/webhooks/order-created-new-testing-my-newy-tesingggggg-toc-hejcjk.md) | Triggered when a new order is created |
| [orderUpdated](../../../doc/events/webhooks/webhooks/order-updated.md) | Triggered when an order is updated |
| [paymentCompleted](../../../doc/events/webhooks/webhooks/payment-completed.md) | Triggered when a payment is successfully processed |
| [primitiveCollectionEvent](../../../doc/events/webhooks/webhooks/primitive-collection-event.md) | Demonstrates oneOf across enum(string), integer, and array types. |

## SDK Usage Example

```ts
import express, { Request, Response } from 'express';
import {
  convertExpressRequest,
  WebhooksHandler,
  WebhooksParsingResult,
} from 'package-wesley-key-ts-new';

const app = express();
app.use(express.json());

const handler = new WebhooksHandler('hmac-secret-key');

app.post('/webhooks', (req: Request, res: Response) => {
  // Use the provided handler to verify and parse the incoming event
  const result = handler.verifyAndParseEvent(convertExpressRequest(req));

  if (WebhooksParsingResult.isOrderCreatedNewTestingMyNewyTesinggggggTocHejcjkEvent(result)) {
    // Result narrowed down to type OrderCreatedNewTestingMyNewyTesinggggggTocHejcjk
    res.status(200).send(result);
  } else if (WebhooksParsingResult.isOrderUpdatedEvent(result)) {
    // Result narrowed down to type OrderUpdated
    res.status(200).send(result);
  } else if (WebhooksParsingResult.isPaymentCompletedEvent(result)) {
    // Result narrowed down to type PaymentCompleted
    res.status(200).send(result);
  } else if (WebhooksParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
    res.status(400).send(result);
  } else if (WebhooksParsingResult.isSignatureVerificationFailure(result)) {
    // Result narrowed down to type SignatureVerificationFailure
    res.status(400).send(result);
  }
});
```



# Payment Status Updated

Triggered when a payment status is updated via POST method

## Signature Verification

This event uses the `HMAC Signature Verifier` for request verification. The event includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [PaymentStatusUpdatedEvent](../../../../doc/models/payment-status-updated-event.md).

## Payload Example

```json
{
  "paymentStatusId": "ps_123",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

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
  } else if (WebhooksAParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
    res.status(400).send(result);
  } else if (WebhooksAParsingResult.isSignatureVerificationFailure(result)) {
    // Result narrowed down to type SignatureVerificationFailure
    res.status(400).send(result);
  }
});
```

## Accepted Server Responses

The server should responds with one of the following status codes:

| Status Code | Description |
|  --- | --- |
| 200 | Event processed successfully |
| 422 | Event processing failed |


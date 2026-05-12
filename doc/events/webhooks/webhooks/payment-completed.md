
# Payment Completed

Triggered when a payment is successfully processed

## Signature Verification

This event uses the `HMAC Signature Verifier` for request verification. The event includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [PaymentCompletedEvent](../../../../doc/models/payment-completed-event.md).

## Payload Example

```json
{
  "paymentId": 91,
  "eventType": "payment.completed",
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
  WebhooksHandler,
  WebhooksParsingResult,
} from 'package-wesley-key-ts-new';

const app = express();
app.use(express.json());

const handler = new WebhooksHandler('hmac-secret-key');

app.post('/webhooks', (req: Request, res: Response) => {
  // Use the provided handler to verify and parse the incoming event
  const result = handler.verifyAndParseEvent(convertExpressRequest(req));

  if (WebhooksParsingResult.isPaymentCompletedEvent(result)) {
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

## Accepted Server Responses

The server should responds with one of the following status codes:

| Status Code | Description |
|  --- | --- |
| 200 | Event processed successfully |
| 400 | Malformed or invalid payload |
| 401 | Signature verification failed or missing |


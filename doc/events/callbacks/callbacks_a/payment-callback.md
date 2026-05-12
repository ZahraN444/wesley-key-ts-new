
# Payment Callback

Called when payment processing is complete

## Signature Verification

This event uses the `HMAC Signature Verifier` for request verification. The event includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [PaymentCallback](../../../../doc/models/payment-callback.md).

## Payload Example

```json
{
  "orderId": "order_789",
  "paymentStatus": "success",
  "transactionId": "txn_abc123",
  "amount": 59.98,
  "currency": "USD",
  "timestamp": "2025-09-19T10:35:00Z",
  "failureReason": "failureReason2",
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
  CallbacksAHandler,
  CallbacksAParsingResult,
  convertExpressRequest,
} from 'package-wesley-key-ts-new';

const app = express();
app.use(express.json());

const handler = new CallbacksAHandler('hmac-secret-key');

app.post('/callbacks', (req: Request, res: Response) => {
  // Use the provided handler to verify and parse the incoming event
  const result = handler.verifyAndParseEvent(convertExpressRequest(req));

  if (CallbacksAParsingResult.isPaymentCallbackEvent(result)) {
    // Result narrowed down to type PaymentCallback
    res.status(200).send(result);
  } else if (CallbacksAParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
    res.status(400).send(result);
  } else if (CallbacksAParsingResult.isSignatureVerificationFailure(result)) {
    // Result narrowed down to type SignatureVerificationFailure
    res.status(400).send(result);
  }
});
```

## Accepted Server Responses

The server should responds with one of the following status codes:

| Status Code | Description |
|  --- | --- |
| 200 | Callback received successfully |
| 400 | Invalid callback data |


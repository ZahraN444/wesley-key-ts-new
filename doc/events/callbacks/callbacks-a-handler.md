## Callbacks A Handler

Payment and fulfillment callback group with custom verification

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [paymentCallback](../../../doc/events/callbacks/callbacks_a/payment-callback.md) | Called when payment processing is complete |
| [fulfillmentCallback](../../../doc/events/callbacks/callbacks_a/fulfillment-callback.md) | Called when order processing is complete |

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
  } else if (CallbacksAParsingResult.isFulfillmentCallbackEvent(result)) {
    // Result narrowed down to type FulfillmentCallback
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


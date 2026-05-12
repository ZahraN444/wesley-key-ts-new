## Callbacks B Handler

Notification delivery callback group with discriminator mapping

Events in this group are uniquely identified by the `notificationType` field.

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description | Event Identifier |
|  --- | --- | --- |
| [emailNotificationCallback](../../../doc/events/callbacks/callbacks_b/email-notification-callback.md) | Called when email notification delivery is complete | email |
| [smsNotificationCallback](../../../doc/events/callbacks/callbacks_b/sms-notification-callback.md) | Called when SMS notification delivery is complete | sms |

## SDK Usage Example

```ts
import express, { Request, Response } from 'express';
import {
  CallbacksBHandler,
  CallbacksBParsingResult,
  convertExpressRequest,
} from 'package-wesley-key-ts-new';

const app = express();
app.use(express.json());

const handler = new CallbacksBHandler('hmac-secret-key');

app.post('/callbacks', (req: Request, res: Response) => {
  // Use the provided handler to verify and parse the incoming event
  const result = handler.verifyAndParseEvent(convertExpressRequest(req));

  if (CallbacksBParsingResult.isEmailNotificationCallbackEvent(result)) {
    // Result narrowed down to type EmailNotificationCallback
    res.status(200).send(result);
  } else if (CallbacksBParsingResult.isSmsNotificationCallbackEvent(result)) {
    // Result narrowed down to type SmsNotificationCallback
    res.status(200).send(result);
  } else if (CallbacksBParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
    res.status(400).send(result);
  } else if (CallbacksBParsingResult.isSignatureVerificationFailure(result)) {
    // Result narrowed down to type SignatureVerificationFailure
    res.status(400).send(result);
  }
});
```


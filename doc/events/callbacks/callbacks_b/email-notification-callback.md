
# Email Notification Callback

Called when email notification delivery is complete

## Signature Verification

This event uses the `HMAC Signature Verifier` for request verification. The event includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [NotificationCallback](../../../../doc/models/notification-callback.md).

## Payload Example

```json
{
  "notificationType": "email",
  "subject": "Order Coonfirmation",
  "message": "msg_email_789",
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
  } else if (CallbacksBParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
    res.status(400).send(result);
  } else if (CallbacksBParsingResult.isSignatureVerificationFailure(result)) {
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
| 422 | Callback processing failed |


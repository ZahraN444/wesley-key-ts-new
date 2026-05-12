## Webhooks C Handler

Primitive and collection variant webhook group.

## Signature Verification

This handler uses the `HMAC Signature Verifier` for request verification. Each event in this group includes an `X-Webhook-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name |
|  --- |
| [stringEvent](../../../doc/events/webhooks/webhooks_c/string-event.md) |
| [intEvent](../../../doc/events/webhooks/webhooks_c/int-event.md) |
| [numberListEvent](../../../doc/events/webhooks/webhooks_c/number-list-event.md) |
| [stringMapEvent](../../../doc/events/webhooks/webhooks_c/string-map-event.md) |

## SDK Usage Example

```ts
import express, { Request, Response } from 'express';
import {
  convertExpressRequest,
  WebhooksCHandler,
  WebhooksCParsingResult,
} from 'package-wesley-key-ts-new';

const app = express();
app.use(express.json());

const handler = new WebhooksCHandler('hmac-secret-key');

app.post('/webhooks', (req: Request, res: Response) => {
  // Use the provided handler to verify and parse the incoming event
  const result = handler.verifyAndParseEvent(convertExpressRequest(req));

  if (WebhooksCParsingResult.isStringEventEvent(result)) {
    // Result narrowed down to type StringEvent
    res.status(200).send(result);
  } else if (WebhooksCParsingResult.isIntEventEvent(result)) {
    // Result narrowed down to type IntEvent
    res.status(200).send(result);
  } else if (WebhooksCParsingResult.isNumberListEventEvent(result)) {
    // Result narrowed down to type NumberListEvent
    res.status(200).send(result);
  } else if (WebhooksCParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
    res.status(400).send(result);
  } else if (WebhooksCParsingResult.isSignatureVerificationFailure(result)) {
    // Result narrowed down to type SignatureVerificationFailure
    res.status(400).send(result);
  }
});
```


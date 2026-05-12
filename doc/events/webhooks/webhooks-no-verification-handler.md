## Webhooks No Verification Handler

Demo group with no payload verification (unsigned webhooks).

## Events

Events available in this group. Subscribe to receive webhook notifications when these events occur.

| Name | Description |
|  --- | --- |
| [auditLogEvent](../../../doc/events/webhooks/webhooks_no_verification/audit-log-event.md) | Demonstrates an event without signature verification. |
| [rootLevelPrimitiveOneOfEvent](../../../doc/events/webhooks/webhooks_no_verification/root-level-primitive-one-of-event.md) | Root-level oneOf across primitives and collections of primitives/enums. |

## SDK Usage Example

```ts
import express, { Request, Response } from 'express';
import {
  convertExpressRequest,
  WebhooksNoVerificationHandler,
  WebhooksNoVerificationParsingResult,
} from 'package-wesley-key-ts-new';

const app = express();
app.use(express.json());

const handler = new WebhooksNoVerificationHandler();

app.post('/webhooks', (req: Request, res: Response) => {
  // Use the provided handler to parse the incoming event
  const result = handler.parseEvent(convertExpressRequest(req));

  if (WebhooksNoVerificationParsingResult.isAuditLogEventEvent(result)) {
    // Result narrowed down to type AuditLogEvent
    res.status(200).send(result);
  } else if (WebhooksNoVerificationParsingResult.isRootLevelPrimitiveOneOfEventEvent(result)) {
    // Result narrowed down to type RootLevelPrimitiveOneOfEvent
    res.status(200).send(result);
  } else if (WebhooksNoVerificationParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
    res.status(400).send(result);
  }
});
```


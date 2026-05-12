
# Root Level Primitive One of Event

Root-level oneOf across primitives and collections of primitives/enums.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [RootLevelOneOfPrimitiveEventRootLevelPrimitiveOneOfBody](../../../../doc/models/containers/root-level-one-of-primitive-event-root-level-primitive-one-of-body.md).

## Payload Example

```json
"on"
```

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

  if (WebhooksNoVerificationParsingResult.isRootLevelPrimitiveOneOfEventEvent(result)) {
    // Result narrowed down to type RootLevelPrimitiveOneOfEvent
    res.status(200).send(result);
  } else if (WebhooksNoVerificationParsingResult.isEventTypeUnknown(result)) {
    // Result narrowed down to type UnknownEvent
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


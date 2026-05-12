
# Audit Log Event

Demonstrates an event without signature verification.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [AuditLogEvent](../../../../doc/models/audit-log-event.md).

## Payload Example

```json
{
  "eventType": "audit.log",
  "actor": "actor6",
  "action": "action6",
  "context": {
    "key1": "val1",
    "key2": "val2"
  },
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


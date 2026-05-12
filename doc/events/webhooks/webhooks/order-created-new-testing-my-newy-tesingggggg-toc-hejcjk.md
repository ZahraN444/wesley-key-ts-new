
# Order Created New Testing My Newy Tesingggggg Toc Hejcjk

Triggered when a new order is created

## Signature Verification

This event uses the `HMAC Signature Verifier` for request verification. The event includes an `X-Signature` header that will be validated using your shared `secret-key` to ensure request authenticity.

## Headers

This event's request contains the following headers.

| Name |
|  --- |
| Content-Type |

## Payload Type

This event's request payload is of type [OrderCreatedEvent](../../../../doc/models/order-created-event.md).

## Payload Example

```json
{
  "orderId": null,
  "fulfillmentStatus": "fulfilled",
  "carrier": "FedEx",
  "estimatedDelivery": "2025-09-22",
  "timestamp": "2025-09-19T14:00:00Z",
  "totalWeight": 12.75,
  "price": 199.99,
  "quantity": 5,
  "longId": 9223372036854775807,
  "fragile": true,
  "items": [
    "item1",
    "item2"
  ],
  "packages": [
    {
      "packageId": "PKG123",
      "weight": 2.5
    }
  ],
  "address": {
    "street": "123 Main St",
    "city": "New York",
    "zip": "10001"
  },
  "metadata": {
    "customField1": "value",
    "customField2": 123
  },
  "attributes": {
    "color": "red",
    "size": "XL"
  },
  "deliveryDetails": {
    "method": "express",
    "eta": "2025-09-21T12:00:00Z"
  },
  "trackingNumber": "trackingNumber4",
  "scopes": [
    "test1",
    "selection",
    "file_requests.read"
  ],
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

  if (WebhooksParsingResult.isOrderCreatedNewTestingMyNewyTesinggggggTocHejcjkEvent(result)) {
    // Result narrowed down to type OrderCreatedNewTestingMyNewyTesinggggggTocHejcjk
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
| 422 | Event processing failed |


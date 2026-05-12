
# Fulfillment Callback

*This model accepts additional fields of type unknown.*

## Structure

`FulfillmentCallback`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `orderId` | `string \| null` | Required | - |
| `fulfillmentStatus` | [`FulfillmentStatus`](../../doc/models/fulfillment-status.md) | Required | - |
| `trackingNumber` | `string \| null \| undefined` | Optional | - |
| `carrier` | `string \| undefined` | Optional | - |
| `scopes` | [`OauthScopeOauthACG[] \| null \| undefined`](../../doc/models/oauth-scope-oauth-acg.md) | Optional | List of scopes that apply to the OAuth token<br><br>**Constraints**: *Unique Items Required* |
| `estimatedDelivery` | `string \| undefined` | Optional | - |
| `timestamp` | `string \| undefined` | Optional | - |
| `document` | `string \| undefined` | Optional | Binary file upload |
| `totalWeight` | `number \| undefined` | Optional | - |
| `price` | `number \| undefined` | Optional | - |
| `quantity` | `number \| undefined` | Optional | - |
| `longId` | `bigint \| undefined` | Optional | - |
| `fragile` | `boolean \| undefined` | Optional | - |
| `notes` | `string \| null \| undefined` | Optional | Explicitly nullable field |
| `items` | `string[] \| undefined` | Optional | - |
| `packages` | [`Package[] \| undefined`](../../doc/models/package.md) | Optional | - |
| `address` | [`Address \| undefined`](../../doc/models/address.md) | Optional | - |
| `metadata` | `unknown \| undefined` | Optional | - |
| `attributes` | `Record<string, string> \| undefined` | Optional | - |
| `deliveryDetails` | [`FulfillmentCallbackDeliveryDetails \| undefined`](../../doc/models/containers/fulfillment-callback-delivery-details.md) | Optional | This is a container for one-of cases. |
| `orderIdd` | `string \| null \| undefined` | Optional | - |
| `fulfillmentStatuss` | [`FulfillmentStatuss \| undefined`](../../doc/models/fulfillment-statuss.md) | Optional | - |
| `trackingNumberr` | `string \| null \| undefined` | Optional | - |
| `carrierr` | `string \| undefined` | Optional | - |
| `scopess` | [`OauthScopeOauthACG[] \| null \| undefined`](../../doc/models/oauth-scope-oauth-acg.md) | Optional | List of scopes that apply to the OAuth token<br><br>**Constraints**: *Unique Items Required* |
| `estimatedDeliveryy` | `string \| undefined` | Optional | - |
| `timestampp` | `string \| undefined` | Optional | - |
| `documentt` | `string \| undefined` | Optional | Binary file upload |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "orderId": null,
  "fulfillmentStatus": "fulfilled",
  "carrier": "FedEx",
  "estimatedDelivery": "2025-09-22",
  "timestamp": "09/19/2025 14:00:00",
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
  "fulfillmentStatuss": "fulfilled",
  "carrierr": "FedEx",
  "estimatedDeliveryy": "2025-09-22",
  "timestampp": "09/19/2025 14:00:00",
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


# Orders

Order management operations

```ts
const ordersApi = new OrdersApi(client);
```

## Class Name

`OrdersApi`


# Create Order

Creates a new order and triggers callbacks for payment processing

```ts
async createOrder(
  body: CreateOrderRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Order>>
```

## Authentication

This endpoint requires [ApiKey](../../doc/auth/custom-header-signature.md) **OR** [BearerAuth](../../doc/auth/oauth-2-bearer-token.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateOrderRequest`](../../doc/models/create-order-request.md) | Body, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**201**: Order created successfully

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Order`](../../doc/models/order.md).

## Related Callbacks

| Name | Description |
|  --- | --- |
| [Payment Callback](../../doc/events/callbacks/callbacks_a/payment-callback.md) | Called when payment processing is complete |
| [Fulfillment Callback](../../doc/events/callbacks/callbacks_a/fulfillment-callback.md) | Called when order processing is complete |
| [Email Notification Callback](../../doc/events/callbacks/callbacks_b/email-notification-callback.md) | Called when email notification delivery is complete |
| [Sms Notification Callback](../../doc/events/callbacks/callbacks_b/sms-notification-callback.md) | Called when SMS notification delivery is complete |

## Example Usage

```ts
const body: CreateOrderRequest = {
  customerId: 'cust_12345',
  items: [
    {
      productId: 'prod_001',
      quantity: 2,
      price: 29.99,
    }
  ],
  callbackUrl: 'https://merchant.example.com/callbacks/payment',
};

try {
  const response = await ordersApi.createOrder(body);

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
    if (error instanceof CustomError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Invalid request | [`CustomError`](../../doc/models/custom-error.md) |


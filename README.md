
# Getting Started with Webhooks and Callbacks API

## Introduction

A comprehensive API demonstrating webhooks and callbacks patterns.

### Webhooks

Webhooks allow your application to receive real-time notifications when certain events occur.

### Callbacks

Callbacks are used for asynchronous operations where the API will call back to your provided URL when the operation completes.

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install package-wesley-key-ts-new@4.1.0
```

For additional package details, see the [Npm page for the package-wesley-key-ts-new@4.1.0 npm](https://www.npmjs.com/package/package-wesley-key-ts-new/v/4.1.0).

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| timeout | `number` | Timeout for API calls.<br>*Default*: `50000` |
| httpClientOptions | [`Partial<HttpClientOptions>`](doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| logging | [`PartialLoggingOptions`](doc/partial-logging-options.md) | Logging Configuration to enable logging |
| apiKeyCredentials | [`ApiKeyCredentials`](doc/auth/custom-header-signature.md) | The credential object for apiKey |
| bearerAuthCredentials | [`BearerAuthCredentials`](doc/auth/oauth-2-bearer-token.md) | The credential object for bearerAuth |

The API client can be initialized as follows:

### Code-Based Client Initialization

```ts
import { Client, LogLevel } from 'package-wesley-key-ts-new';

const client = new Client({
  apiKeyCredentials: {
    'X-API-Key': 'X-API-Key'
  },
  bearerAuthCredentials: {
    accessToken: 'AccessToken'
  },
  timeout: 50000,
  logging: {
    logLevel: LogLevel.Info,
    logRequest: {
      logBody: true
    },
    logResponse: {
      logHeaders: true
    }
  },
});
```

### Configuration-Based Client Initialization

```ts
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'package-wesley-key-ts-new';

// Provide absolute path for the configuration file
const absolutePath = path.resolve('./config.json');

// Read the configuration file content
const fileContent = fs.readFileSync(absolutePath, 'utf-8');

// Initialize client from JSON configuration content
const client = Client.fromJsonConfig(fileContent);
```

See the [Configuration-Based Client Initialization](doc/configuration-based-client-initialization.md) section for details.

### Environment-Based Client Initialization

```ts
import * as dotenv from 'dotenv';
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'package-wesley-key-ts-new';

// Optional - Provide absolute path for the .env file
const absolutePath = path.resolve('./.env');

if (fs.existsSync(absolutePath)) {
  // Load environment variables from .env file
  dotenv.config({ path: absolutePath, override: true });
}

// Initialize client using environment variables
const client = Client.fromEnvironment(process.env);
```

See the [Environment-Based Client Initialization](doc/environment-based-client-initialization.md) section for details.

## Authorization

This API uses the following authentication schemes.

* [`ApiKey (Custom Header Signature)`](doc/auth/custom-header-signature.md)
* [`BearerAuth (OAuth 2 Bearer token)`](doc/auth/oauth-2-bearer-token.md)

## List of APIs

* [Orders](doc/controllers/orders.md)

## Webhooks

* [Webhooks](doc/events/webhooks/webhooks-handler.md)
* [Webhooks A](doc/events/webhooks/webhooks-a-handler.md)
* [Webhooks B](doc/events/webhooks/webhooks-b-handler.md)
* [Webhooks C](doc/events/webhooks/webhooks-c-handler.md)
* [Webhooks No Verification](doc/events/webhooks/webhooks-no-verification-handler.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](doc/http-client-options.md)
* [RetryConfiguration](doc/retry-configuration.md)
* [ProxySettings](doc/proxy-settings.md)
* [Configuration-Based Client Initialization](doc/configuration-based-client-initialization.md)
* [Environment-Based Client Initialization](doc/environment-based-client-initialization.md)
* [PartialLoggingOptions](doc/partial-logging-options.md)
* [PartialRequestLoggingOptions](doc/partial-request-logging-options.md)
* [PartialResponseLoggingOptions](doc/partial-response-logging-options.md)
* [LoggerInterface](doc/logger-interface.md)

### HTTP

* [HttpRequest](doc/http-request.md)

### Utilities

* [ApiResponse](doc/api-response.md)
* [ApiError](doc/api-error.md)


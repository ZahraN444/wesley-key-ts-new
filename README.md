
# Getting Started with Cypress Test API

## Introduction

This is a sample API to demonstrate an OpenAPI spec with multiple endpoints and a custom model.

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install package-wesley-key-ts-new@3.0.6
```

For additional package details, see the [Npm page for the package-wesley-key-ts-new@3.0.6 npm](https://www.npmjs.com/package/package-wesley-key-ts-new/v/3.0.6).

## Test the SDK

To validate the functionality of this SDK, you can execute all tests located in the `test` directory. This SDK utilizes `Jest` as both the testing framework and test runner.

To run the tests, navigate to the root directory of the SDK and execute the following command:

```bash
npm run test
```

Or you can also run tests with coverage report:

```bash
npm run test:coverage
```

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| defaultHost | `string` | *Default*: `'www.example.com'` |
| environment | [`Environment`](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/README.md#environments) | The API environment. <br> **Default: `Environment.Production`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `0` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |

The API client can be initialized as follows:

### Code-Based Client Initialization

```ts
import { Client, Environment } from 'package-wesley-key-ts-new';

const client = new Client({
  timeout: 0,
  environment: Environment.Production,
  defaultHost: 'www.example.com',
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

See the [Configuration-Based Client Initialization](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/configuration-based-client-initialization.md) section for details.

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

See the [Environment-Based Client Initialization](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/environment-based-client-initialization.md) section for details.

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| Production | **Default** |

## List of APIs

* [API](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/controllers/api.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/proxy-settings.md)
* [Configuration-Based Client Initialization](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/configuration-based-client-initialization.md)
* [Environment-Based Client Initialization](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/environment-based-client-initialization.md)

### HTTP

* [HttpRequest](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/api-response.md)
* [ApiError](https://www.github.com/ZahraN444/wesley-key-ts-new/tree/3.0.6/doc/api-error.md)



# Custom Header Signature



Documentation for accessing and setting credentials for ApiKey.

## Auth Credentials

| Name | Type | Description | Setter |
|  --- | --- | --- | --- |
| X-API-Key | `string` | API key for authentication | `xAPIKey` |



**Note:** Auth credentials can be set using `apiKeyCredentials` object in the client.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```ts
import { Client } from 'package-wesley-key-ts-new';

const client = new Client({
  apiKeyCredentials: {
    'X-API-Key': 'X-API-Key'
  },
});
```



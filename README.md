## Kloutit SDK

Kloutit is an AI-powered B2B SaaS that enables online merchants to effectively and efficiently defend and prevent chargebacks.

This SDK allows your organization to integrate with Kloutit, so your cases could be automatically created into our system to take profit of all the following profits.

## Installation

// ALEXIS REVISAR ESTO
To install Kloutit SDK you can run the following npm command.

```
npm install kloutit-sdk@latest
```

## Prerequisites

To be able to use any Kloutit SDK function, your organization must be registered into our system and SDK client keys for the organization must be created. You can register your organization by following a few simple steps from https://clients.kloutit.com.

Once your organization is successfully registered, you will be able to configure the SDK connection from the menu `Organization > Integration`. You will need to:

- Create a new client credentials
- Add the allowed domains

## Usage

To use the Kloutit SDK client, you will need to instantiate the KloutitLoginApi to obtain a valid accessToken (expires at 30m, then you can generate a new one). With this accessToken you will be able to instantiate the rest of the available APIs and make your actions.

### Sample code Login

```
import { KloutitEnvironment, KloutitLoginApi } from 'kloutit-sdk';

// Define your secret values (it should come from an .env or similar)
const CLIENT_ID = '22311cca-9951-42dd-bc9b-bd0574335b55';
const CLIENT_SECRET = '6#.n3dcm-x4hc3Y0SrA/UR?DzggfM;';
const ORGANIZATION_ID = '660055bca25e9c2da9b87944';

// Create the login api instance (for development in this case)
const kloutitLogin = new KloutitLoginApi(KloutitEnvironment.development);

// Define the Base64 token auth
const base64Auth = Buffer.from(`${CLIENT_ID}:${CLIENT_SECRET}`).toString('base64');

// Define the Authorization header
const headers = { Authorization: `Basic ${base64Auth}` };

// Make the login call
const loginResponse = await this.kloutitLogin.login(
    ORGANIZATION_ID,
    { grant_type: 'client_credentials' },
    { headers }
);

const accessToken = loginResponse.data['accessToken'];
```

### Sample code other calls

Once you have the accessToken with the Login call, you can use it to make other calls, for instance, to create a case.

```
import { KloutitEnvironment, KloutitCaseApi } from 'kloutit-sdk';

// Create the desired api instance (for development in this case)
const kloutitCase = new KloutitCaseApi(KloutitEnvironment.development);

// Define the Authorization header
const headers = { Authorization: `Bearer ${accessToken}` };

// Make the call with the requested body
const caseResponse = await this.kloutitCase.createCase({...body});
```

### Documentation

In this document, you will be able to see all the available methods and all the parameters needed, so you know exactly what you need to do. If you have any doubts, please, don't hesitate to contact us so we can help you, or leave us any comment so we can improve your experience.

### Autocompletion

If you use an IDE such as VSCode, you will be able to see all the autocompletion for methods and parameters, so you know exactly what the call is expecting to receive.

### Security

Kloutit SDK does not store or refresh access tokens. Storing and refreshing access tokens is responsibility of the SDK consumer.

Please, if you discover any security issues, report them to security@kloutit.com as soon as possible.

### License
BSD-3-Clause
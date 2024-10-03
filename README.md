## Kloutit SDK

Kloutit is an AI-powered B2B SaaS that enables online merchants to effectively and efficiently defend and prevent chargebacks.

This SDK allows your organization to integrate with Kloutit, so your cases could be automatically created into our system to take profit of all the following profits.

## Installation

To install Kloutit SDK you can run the following composer command.

```
composer require kloutit/kloutit-sdk-php
```

## Prerequisites

To be able to use any Kloutit SDK function, your organization must be registered into our system and SDK client keys for the organization must be created. You can register your organization by following a few simple steps from https://app.kloutit.com.

Once your organization is successfully registered, you will be able to configure the SDK connection from the menu `My organization > Kloutit SDK`. You will need to:

- Create a new client credentials
- Add the allowed domains

## Usage

To use the Kloutit SDK client, you will need to instantiate the KloutitLoginApi to obtain a valid accessToken (expires at 30m, then you can generate a new one). With this accessToken you will be able to instantiate the rest of the available APIs and make your actions.

### Sample code Login

```
<?php
$clientId = '22311cca-9951-42dd-bc9b-bd0574335b55';
$clientSecret = '6#.n3dcm-x4hc3Y0SrA/UR?DzggfM;';
$organizationId = '660055bca25e9c2da9b87944';

// If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
// This is optional, `GuzzleHttp\Client` will be used as default.
$client = new GuzzleHttp\Client();

// Configure Login http basic authorization
$loginConfig = OpenAPI\Client\Configuration::getDefaultConfiguration()
              ->setUsername($clientId)
              ->setPassword($clientSecret);

$kloutitLogin = new OpenAPI\Client\Api\KloutitLoginApi(
    OpenAPI\Client\KloutitEnvironment::Development,
    $client,
    $loginConfig
);
$kloutitLoginBody = new \OpenAPI\Client\Model\KloutitLoginBody([
    'grant_type' => 'client_credentials'
]);

$accessToken;

// Login
try {
    echo "Getting Kloutit access token for organization $organizationId";
    $loginResponse = $kloutitLogin->login($organizationId, $kloutitLoginBody);

    $accessToken = $loginResponse->getAccessToken();
    echo "Access token successfully retrieved!";
} catch (Exception $e) {
    echo "Error trying to login to Kloutit SDK.";
    throw new Exception($e->getMessage());
}
```

### Sample code other calls

Once you have the accessToken with the Login call, you can use it to make other calls, for instance, to create a case.

```
<?php
// Configure Bearer (JWT) authorization: bearer
$caseConfig = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken($accessToken);

$kloutitCase = new OpenAPI\Client\Api\KloutitCaseApi(
    OpenAPI\Client\KloutitEnvironment::Development,
    $client,
    $caseConfig
);
$kloutitCaseBody = new \OpenAPI\Client\Model\KloutitCaseBody([
    'chargeback_reason' => 'PRODUCT_SERVICE_NOT_RECEIVED',
    'customer_email' => 'kloutit-php@example.com',
    'customer_name' => 'PHP SDK sample',
    'dispute_amount' => [
        'currency' => 'EUR',
        'value' => 10,
    ],
    'expedient_number' => 'EXPPHP0001',
    'is3_ds_purchase' => true,
    'is_charge_refundable' => true,
    'notification_date' => '2024-03-22T11:31:22.347Z',
    'organization_id' => $organizationId,
    'purchase_amount' => [
        'currency' => 'EUR',
        'value' => 10,
    ],
    'purchase_date' => '2024-03-22T11:31:22.347Z',
    'transaction_date' => '2024-03-22T11:31:22.347Z',
    'deadline' => '2024-03-22T11:31:22.347Z',
]);

try {
    $kloutitCase->createCase($kloutitCaseBody);
    echo 'Case successfully created into Kloutit!';
} catch (Exception $e) {
    echo "Error trying to create case into Kloutit.";
    throw new Exception($e->getMessage());
}
```

### Documentation

In this document, you will be able to see all the available methods and all the parameters needed, so you know exactly what you need to do. If you have any doubts, please, don't hesitate to contact us so we can help you, or leave us any comment so we can improve your experience.

### Autocompletion

If you use an IDE such as VSCode, you will be able to see all the autocompletion for methods and parameters, so you know exactly what the call is expecting to receive.

### Security

Kloutit SDK does not store or refresh access tokens. Storing and refreshing access tokens is responsibility of the SDK consumer.

Please, if you discover any security issues, report them to security@kloutit.com as soon as possible.

### License

Apache 2.0

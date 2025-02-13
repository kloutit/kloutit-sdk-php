## Kloutit SDK

Kloutit is an AI-powered B2B SaaS that enables online merchants to effectively and efficiently defend and prevent chargebacks.

This SDK allows your organization to integrate with Kloutit, so your cases could be automatically updated into our system to take profit of all the following profits.

## Installation

To install Kloutit SDK you can run the following composer command.

```
composer require kloutit/kloutit-sdk-php
```

## Prerequisites

To be able to use any Kloutit SDK function, your organization must be registered into our system and SDK client key for the organization must be created. You can register your organization by following a few simple steps from https://app.kloutit.com.

Once your organization is successfully registered, you will need to create new client key from the menu `My organization > Developers`.

## Usage

To use the Kloutit SDK client, you will need to instantiate the KloutitConfiguration using the client key and make your actions.

### Sample update call code

Once you have the apiKey, you can use it to instantiate the KloutitCaseApi and make calls.

```php
<?php
// Require composer autoloader
require 'vendor/autoload.php';

use Kloutit\Configuration as KloutitConfiguration;
use Kloutit\Api\KloutitCaseApi;
use Kloutit\Model\UpdateCaseParams;
use Kloutit\Model\CaseSector;
use Kloutit\Model\Currencies;

$apiKey = 'YOUR_API_KEY';
$expedientNumber = 'EXPEDIENT_NUMBER';

// If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
// This is optional, `GuzzleHttp\Client` will be used as default.
$client = new GuzzleHttp\Client();

// Configure api key auth
$config = KloutitConfiguration::getDefaultConfiguration()
    ->setApiKey($apiKey);

// Create KloutitCaseApi instance
$kloutitCase = new KloutitCaseApi(
    $client,
    $config,
);

// Update case
$kloutitCaseBody = new UpdateCaseParams([
    'sector' => CaseSector::TECHNOLOGY,
    'filialIdentifier' => 'B12345678', // If you do not have filials in your organization, leave this field empty
    'transactionDate' => (new DateTime())->format(DateTime::ATOM), // UTC date in ISO 8601 format, e.g: '2025-01-01T10:00:00.000Z'
    'bankName' => 'Sample bank',
    'cardBrand' => 'Sample card brand',
    'last4Digits' => '1234',
    'is3DSPurchase' => true,
    'purchaseDate' => '2025-01-01T10:00:00.000Z',
    'purchaseAmount' => [
        'currency' => Currencies::EUR,
        'value' => 10
    ],
    'isChargeRefundable' => true,
    'customerName' => 'Node SDK sample',
    'customerEmail' => 'kloutit-node@example.com',
    'customerPhone' => '612345678',
    'additionalInfo' => 'Some optional additional info',
    'communications' => [
        [
            'sender' => 'Sender name',
            'content' => 'Communication content',
            'date' => '2025-01-01T10:00:00.000Z',
        ]
    ],
    'product' => 'Sample product',
    'service' => 'Sample service',
    'shippingCity' => 'Barcelona',
    'shippingProvince' => 'Barcelona',
    'shippingPostalCode' => '08000',
    'deliveryConfirmation' => true,
    'shippingDate' => '2025-01-01T10:00:00.000Z',
    'deliveryDate' => '2025-01-01T10:00:00.000Z',
    'deliveryCompany' => 'Sample company',
]);

try {
    $kloutitCase->updateCase($expedientNumber,$kloutitCaseBody);
    echo "Case successfully updated into Kloutit!\n";
} catch (Exception $e) {
    echo "Error trying to update case into Kloutit.\n";
    throw new Exception($e->getMessage());
}
```

This example is made for TECHNOLOGY sector. You can find the needed body for each sector here:

- [Digital product](tipologies/DIGITAL_PRODUCT.md)
- [Education](tipologies/EDUCATION.md)
- [Fashion](tipologies/FASHION.md)
- [Food](tipologies/FOOD.md)
- [Gaming](tipologies/GAMING.md)
- [Health & beauty](tipologies/HEALTH_BEAUTY.md)
- [Home](tipologies/HOME.md)
- [Leisure](tipologies/LEISURE.md)
- [Marketplace](tipologies/MARKETPLACE.md)
- [Phone](tipologies/PHONE.md)
- [Software](tipologies/SOFTWARE.md)
- [Sport](tipologies/SPORT.md)
- [Subscription](tipologies/SUBSCRIPTION.md)
- [Supply](tipologies/SUPPLY.md)
- [Technology](tipologies/TECHNOLOGY.md)
- [Transport](tipologies/TRANSPORT.md)
- [Travel Airline](tipologies/TRAVEL_AIRLINE.md)
- [Travel Hotel](tipologies/TRAVEL_HOTEL.md)

### Documentation

In this document, you will be able to see all the available methods and all the parameters needed, so you know exactly what you need to do. If you have any doubts, please, don't hesitate to contact us so we can help you, or leave us any comment so we can improve your experience.

### Autocompletion

If you use an IDE such as VSCode, you will be able to see all the autocompletion for methods and parameters, so you know exactly what the call is expecting to receive.

### Security

Kloutit SDK uses API key for authentication. It is the responsibility of the SDK consumer to keep the API key secure and not expose it in source code, public repositories, or insecure environments.

To ensure the security of your integration:

- Store the API key in environment variables or a secure secret manager.
- Do not share your API key in public source code or with unauthorized third parties.
- Regularly rotate API keys to minimize exposure risks.

Please, if you discover any security issues, report them to support@kloutit.com as soon as possible.

### License

Apache 2.0

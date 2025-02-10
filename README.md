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

use Kloutit\Configuration as KloutitConfiguration;
use Kloutit\Api\KloutitCaseApi
use Kloutit\Model\UpdateCaseParams
use Kloutit\Model\ChargebackReason;
use Kloutit\Model\CaseSector;
use Kloutit\Currencies;

require_once('sdk/vendor/autoload.php');

$apiKey = '99e2f0946cd541b598bdbd61148c850d_6TA8KHQWPzNfMqBBMDP6zEgz6cemNYFirRo7XCwRwnhb6H7KoMkUUNxzfnBS';
$expedientNumber = 'dp_1Qk6O7KkhWp1jIM0kkAqFMkD';

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
    'organization_type' => CaseSector::TECHNOLOGY,
    'expedient_number' => 'EXPPHP0001',
    'notification_date' => '2024-09-22T11:31:22.347Z',
    'deadline' => '2027-09-22T11:31:22.347Z',
    'dispute_amount' => [
        'currency' => Currencies::EUR,
        'value' => 10,
    ],
    'chargeback_reason' => ChargebackReason::PRODUCT_SERVICE_NOT_RECEIVED,
    'transaction_date' => '2024-09-22T11:31:22.347Z',
    'pan_number' => 'PAN000001',
    'transaction_id' => 'TR0000001',
    'bank_name' => 'Sample bank',
    'is3_ds_purchase' => true,
    'purchase_date' => '2024-09-22T11:31:22.347Z',
    'purchase_amount' => [
        'currency' => Currencies::EUR,
        'value' => 10,
    ],

    'product' => 'Sample product', // Product OR service should be informed
    'service' => null, // Product OR service should be informed
    'is_charge_refundable' => true,
    'shipping_city' => 'Barcelona',
    'shipping_province' => 'Barcelona',
    'shipping_postal_code' => '08000',
    'shipping_date' => '2024-09-22T11:31:22.347Z',
    'delivery_company' => 'Sample company',
    'delivery_date' => '2024-09-22T11:31:22.347Z',
    'delivery_confirmation' => true,

    'customer_name' => 'PHP SDK sample',
    'customer_email' => 'kloutit-php@example.com',
    'contact_date' => '2024-09-22T11:31:22.347Z',
    'customer_phone' => '612345678',
    'additional_info' => 'Some optional additional info',
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

Kloutit SDK does not store or refresh access tokens. Storing and refreshing access tokens is responsibility of the SDK consumer.

Please, if you discover any security issues, report them to support@kloutit.com as soon as possible.

### License

Apache 2.0

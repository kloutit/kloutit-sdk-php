### Sample body for Renting Vehicle sector

This is a sample UpdateCaseParams for Renting Vehicle sector with all the parameters it admits.

```php
<?php

use Kloutit\Model\UpdateCaseParams;
use Kloutit\Model\CaseSector;
use Kloutit\Model\Currencies;

$kloutitCase = new UpdateCaseParams([
    'sector' => CaseSector::RENTING_VEHICLE,
    'filialIdentifier' => 'B12345678', // If you do not have filials in your organization, leave this field empty
    'transactionDate' => (new DateTime())->format(DateTime::ATOM), // UTC date
    'bankName' => 'Sample bank',
    'cardBrand' => 'Sample card brand',
    'last4Digits' => '1234',
    'is3DSPurchase' => true,
    'purchaseDate' => (new DateTime())->format(DateTime::ATOM), // UTC date
    'purchaseAmount' => [
        'currency' => Currencies::EUR,
        'value' => 200
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
            'date' => (new DateTime())->format(DateTime::ATOM), // UTC date
        ]
    ],

    'rentalOriginLocation' => 'Madrid Airport',
    'rentalDestinationLocation' => 'Barcelona Airport',
    'rentalPickupDate' => (new DateTime())->format(DateTime::ATOM), // UTC date
    'rentalDeliveryDate' => (new DateTime())->format(DateTime::ATOM), // UTC date
    'privateOwnerRental' => false,
    'rentalOwnerName' => 'Sample Rental Company',
    'rentalCurrency' => 'EUR',
    'rentalAmount' => [
        'currency' => Currencies::EUR,
        'value' => 200
    ],
    'extraDistanceAmount' => [
        'currency' => Currencies::EUR,
        'value' => 25
    ],
    'penaltyAmount' => [
        'currency' => Currencies::EUR,
        'value' => 50
    ],
    'depositAmount' => [
        'currency' => Currencies::EUR,
        'value' => 150
    ],
    'damagesAmount' => [
        'currency' => Currencies::EUR,
        'value' => 75
    ],
    'productBrand' => 'Toyota Corolla',
    'productId' => 'TCR-2024-001',
    'productDescription' => 'Product description',
]);
```
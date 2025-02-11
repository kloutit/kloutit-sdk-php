### Sample body for Travel Hotel sector

This is a sample UpdateCaseParams for Travel Hotel sector with all the parameters it admits.

```php
<?php

use Kloutit\Model\UpdateCaseParams;
use Kloutit\Model\CaseSector;
use Kloutit\Currencies;

$kloutitCase = new UpdateCaseParams([
    'sector' => CaseSector::TRAVEL_HOTEL,
    'filialIdentifier' => 'B12345678', // If you do not have filials in your organization, leave this field empty
    'transactionDate' => new DateTime(),
    'bankName' => 'Sample bank',
    'cardBrand' => 'Sample card brand',
    'last4Digits' => '1234',
    'is3DSPurchase' => true,
    'purchaseDate' => new DateTime(),
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
            'date' => new DateTime(),
        ],
    ],
    'service' => 'Sample service',
    'checkinDate' => '2024-09-22T11:31:22.347Z',
    'checkoutDate' => '2024-09-22T11:31:22.347Z',
    'hotelName' => 'Sample hotel',
    'rate' => 'Sample rate',
    'checkinConfirmation' => true,
    'destinationCountry' => 'Spain',
]);
```

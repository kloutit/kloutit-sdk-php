### Sample body for Fashion sector

This is a sample UpdateCaseParams for Fashion sector with all the parameters it admits.

```php
<?php

use Kloutit\Model\UpdateCaseParams;
use Kloutit\Model\CaseSector;
use Kloutit\Currencies;

$kloutitCase = new UpdateCaseParams([
    'sector' => CaseSector::FASHION,
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
        ]
    ],
    'product' => 'Sample product',
    'shippingCity' => 'Barcelona',
    'shippingProvince' => 'Barcelona',
    'shippingPostalCode' => '08000',
    'shippingDate' => new DateTime(),
    'deliveryConfirmation' => true,
    'deliveryDate' => new DateTime(),
    'deliveryCompany' => 'Sample company'
]);
```

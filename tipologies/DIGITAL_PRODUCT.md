### Sample body for Digital Service / Product sector

This is a sample UpdateCaseParams for Digital Service / Product sector with all the parameters it admits.

```php
<?php

use Kloutit\Model\UpdateCaseParams;
use Kloutit\Model\CaseSector;
use Kloutit\Model\Currencies;

$kloutitCase = new UpdateCaseParams([
    'sector' => CaseSector::DIGITAL_PRODUCT,
    'filialIdentifier' => 'B12345678', // If you do not have filials in your organization, leave this field empty
    'transactionDate' => (new DateTime())->format(DateTime::ATOM), // UTC date
    'bankName' => 'Sample bank',
    'cardBrand' => 'Sample card brand',
    'last4Digits' => '1234',
    'is3DSPurchase' => true,
    'purchaseDate' => (new DateTime())->format(DateTime::ATOM), // UTC date
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
            'date' => (new DateTime())->format(DateTime::ATOM), // UTC date
        ]
    ],
    'product' => 'Sample product',
    'service' => 'Sample service',
    'shippingCity' => 'Barcelona',
    'shippingProvince' => 'Barcelona',
    'shippingPostalCode' => '08000',
    'deliveryConfirmation' => true,
    'shippingDate' => (new DateTime())->format(DateTime::ATOM), // UTC date
    'deliveryDate' => (new DateTime())->format(DateTime::ATOM), // UTC date
    'deliveryCompany' => 'Sample company',
]);
```

### Sample body for Travel Airline sector

This is a sample KloutitCaseBody for Travel Airline sector with all the parameters it admits.

```php
<?php

use Kloutit\Model\KloutitCaseBody;
use Kloutit\KloutitOrganizationType;
use Kloutit\KloutitChargebackReason;

$kloutitCaseBody = new KloutitCaseBody([
    'organization_id' => $organizationId,
    'organization_type' => KloutitOrganizationType::TRAVEL_AIRLINE,
    'expedient_number' => 'EXPPHP0001',
    'notification_date' => '2024-03-22T11:31:22.347Z',
    'deadline' => '2024-03-22T11:31:22.347Z',
    'dispute_amount' => [
        'currency' => 'EUR',
        'value' => 10,
    ],
    'chargeback_reason' => KloutitChargebackReason::PRODUCT_SERVICE_NOT_RECEIVED,
    'transaction_date' => '2024-03-22T11:31:22.347Z',
    'pan_number' => 'PAN000001',
    'transaction_id' => 'TR0000001',
    'bank_name' => 'Sample bank',
    'is3_ds_purchase' => true,
    'purchase_date' => '2024-03-22T11:31:22.347Z',
    'purchase_amount' => [
        'currency' => 'EUR',
        'value' => 10,
    ],

    'service' => 'Sample service',
    'is_charge_refundable' => true,
    'departure_date' => '2024-03-22T11:31:22.347Z',
    'arrival_date' => '2024-03-22T11:31:22.347Z',
    'departure_airport' => 'Sample airport',
    'arrival_airport' => 'Sample airport',
    'rate' => 'Sample rate',
    'checkin_confirmation' => true,
    'destination_country' => 'Spain'

    'customer_name' => 'PHP SDK sample',
    'customer_email' => 'kloutit-php@example.com',
    'contact_date' => '2024-04-22T11:31:22.347Z',
    'customer_phone' => '612345678',
    'additional_info' => 'Some optional additional info',
]);
```

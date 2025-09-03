## Kloutit Clients API SDK

Kloutit is an AI-powered B2B SaaS that enables online merchants to effectively and efficiently defend and prevent chargebacks.

This SDK allows your organization to integrate with Kloutit Clients API v2.0, providing comprehensive case management capabilities including creating cases, uploading files, updating case information, and managing the complete chargeback defense workflow.

## Installation

To install Kloutit SDK you can run the following composer command.

```
composer require kloutit/kloutit-sdk-php
```

## Prerequisites

To be able to use any Kloutit SDK function, your organization must be registered into our system and SDK client key for the organization must be created. You can register your organization by following a few simple steps from https://app.kloutit.com.

Once your organization is successfully registered, you will need to create new client key from the menu `My organization > Developers`.

## Available Endpoints

The Kloutit Clients API v2.0 provides the following main endpoints:

- **Create Case** - Create a new chargeback case
- **Upload File** - Upload supporting documents to a case
- **Upload Product Photo** - Upload product images to a case
- **Update Case** - Update case information with additional data
- **Check Case** - Validate case completeness and get missing fields
- **Submit Completed Case** - Mark case as ready for defense generation
- **Verify Event** - Verify webhook events from Kloutit
- **Download Defense** - Download the generated defense document

## Usage

To use the Kloutit SDK client, you will need to instantiate the KloutitConfiguration using your client API key.

### Creating a New Case

```php
<?php
require 'vendor/autoload.php';

use Kloutit\Configuration as KloutitConfiguration;
use Kloutit\Api\KloutitCaseApi;
use Kloutit\Model\ClientsCreateCaseRequestDto;
use Kloutit\Model\CaseSector;
use Kloutit\Model\Currencies;

$apiKey = 'YOUR_API_KEY';
$client = new GuzzleHttp\Client();

// Configure API key authentication
$config = KloutitConfiguration::getDefaultConfiguration()
    ->setApiKey($apiKey);

// Create KloutitCaseApi instance
$kloutitCase = new KloutitCaseApi($client, $config);

try {
    echo "Creating new case\n";
    $newCaseBody = new ClientsCreateCaseRequestDto([
        'expedientNumber' => 'UNIQUE_CASE_ID',
        'sector' => CaseSector::TECHNOLOGY,
        'chargebackAmount' => [
            'value' => 100,
            'currency' => Currencies::EUR,
        ],
        'chargebackDate' => '2025-01-01T10:00:00.000Z',
        'reasonCode' => '4855',
        // Additional fields based on sector requirements
    ]);
    
    $createdCase = $kloutitCase->createCase($newCaseBody);
    echo "Case created successfully!\n";
} catch (Exception $e) {
    echo "Error creating case: " . $e->getMessage() . "\n";
    throw $e;
}
```

### Updating an Existing Case

```php
<?php
// Configure API key authentication
$config = KloutitConfiguration::getDefaultConfiguration()
    ->setApiKey('YOUR_API_KEY');

// Create KloutitCaseApi instance
$kloutitCase = new KloutitCaseApi(new GuzzleHttp\Client(), $config);

$expedientNumber = 'CASE_EXPEDIENT_NUMBER';

// Update case with additional information
$kloutitCaseBody = new UpdateCaseParams([
    'sector' => CaseSector::TECHNOLOGY,
    'filialIdentifier' => 'B12345678', // If you do not have filials in your organization, leave this field empty
    'transactionDate' => (new DateTime())->format(DateTime::ATOM), // UTC date in ISO 8601 format, e.g: '2025-01-01T10:00:00.000Z'
    'bankName' => 'Sample Bank Name',
    'cardBrand' => 'Sample card brand',
    'last4Digits' => '1234',
    'is3DSPurchase' => true,
    'purchaseDate' => '2025-01-01T10:00:00.000Z',
    'purchaseAmount' => [
        'currency' => Currencies::EUR,
        'value' => 100
    ],
    'isChargeRefundable' => false,
    'customerName' => 'PHP SDK sample',
    'customerEmail' => 'kloutit-php@example.com',
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
    'service' => 'Sample Service Name',
    'shippingCity' => 'Barcelona',
    'shippingProvince' => 'Barcelona',
    'shippingPostalCode' => '08000',
    'deliveryConfirmation' => true,
    'shippingDate' => '2025-01-01T10:00:00.000Z',
    'deliveryDate' => '2025-01-01T10:00:00.000Z',
    'deliveryCompany' => 'Sample delivery company',
]);

try {
    echo "Updating existing case\n";
    $updatedCase = $kloutitCase->updateCase($expedientNumber, $kloutitCaseBody);
    echo "Case updated successfully!\n";
} catch (Exception $e) {
    echo "Error updating case: " . $e->getMessage() . "\n";
    throw $e;
}
```

### Uploading Files to a Case

```php
<?php
use Kloutit\Model\FileCategoryEnum;

try {
    echo "Uploading file to case\n";
    $file = new SplFileObject('/path/to/your/file.pdf');
    $uploadedFile = $kloutitCase->uploadFile(
        'CASE_EXPEDIENT_NUMBER',
        $file,
        FileCategoryEnum::INVOICE
    );
    echo "File uploaded successfully!\n";
} catch (Exception $e) {
    echo "Error uploading file: " . $e->getMessage() . "\n";
    throw $e;
}
```

### Checking Case Completeness

```php
<?php
try {
    echo "Checking case completeness\n";
    $caseStatus = $kloutitCase->checkCase('CASE_EXPEDIENT_NUMBER');
    echo "Case status retrieved successfully!\n";
} catch (Exception $e) {
    echo "Error checking case: " . $e->getMessage() . "\n";
    throw $e;
}
```

### Submitting a Completed Case

```php
<?php
try {
    echo "Submitting completed case\n";
    $kloutitCase->submitCompletedCase('CASE_EXPEDIENT_NUMBER');
    echo "Case submitted successfully!\n";
} catch (Exception $e) {
    echo "Error submitting case: " . $e->getMessage() . "\n";
    throw $e;
}
```
```

## Sector-Specific Requirements

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

## File Upload Specifications

When uploading files to cases:

- **Supported formats**: PDF, JPG, JPEG, PNG
- **Maximum file size**: 10MB
- **Upload method**: multipart/form-data
- **Required parameters**: file and category
- **Available categories**: Based on FileCategoryEnum (INVOICE, PROOF_OF_DELIVERY, etc.)

## Webhook Event Verification

To verify webhook events from Kloutit:

```php
<?php
try {
    echo "Verifying webhook event\n";
    $kloutitCase->verifyEvent($webhookEventData);
    echo "Event verified successfully!\n";
} catch (Exception $e) {
    echo "Event verification failed: " . $e->getMessage() . "\n";
    throw $e;
}
```

## Defense Document Download

Download generated defense documents in different formats:

```php
<?php
try {
    echo "Downloading case defense\n";
    $defenseDocument = $kloutitCase->downloadCaseDefense(
        'PDF', // Format: PDF, DOCX, etc.
        'CASE_EXPEDIENT_NUMBER'
    );
    echo "Defense downloaded successfully!\n";
} catch (Exception $e) {
    echo "Error downloading defense: " . $e->getMessage() . "\n";
    throw $e;
}
```

## API Reference

### Complete Workflow Example

Here's a complete example showing the typical workflow for managing a chargeback case:

```php
<?php
require 'vendor/autoload.php';

use Kloutit\Configuration as KloutitConfiguration;
use Kloutit\Api\KloutitCaseApi;
use Kloutit\Model\ClientsCreateCaseRequestDto;
use Kloutit\Model\UpdateCaseParams;
use Kloutit\Model\CaseSector;
use Kloutit\Model\Currencies;
use Kloutit\Model\FileCategoryEnum;

// Configure API
$config = KloutitConfiguration::getDefaultConfiguration()
    ->setApiKey('YOUR_API_KEY');
$kloutitCase = new KloutitCaseApi(new GuzzleHttp\Client(), $config);

try {
    // 1. Create a new case
    $newCaseBody = new ClientsCreateCaseRequestDto([
        'expedientNumber' => 'CASE_001',
        'sector' => CaseSector::TECHNOLOGY,
        'chargebackAmount' => ['value' => 299.99, 'currency' => Currencies::EUR],
        'chargebackDate' => '2025-01-15T09:00:00.000Z',
        'reasonCode' => '4855'
    ]);
    $newCase = $kloutitCase->createCase($newCaseBody);
    
    // 2. Upload supporting documents
    $invoiceFile = new SplFileObject('/path/to/invoice.pdf');
    $kloutitCase->uploadFile('CASE_001', $invoiceFile, FileCategoryEnum::INVOICE);
    
    // 3. Update case with additional information
    $updateBody = new UpdateCaseParams([
        'purchaseDate' => '2025-01-10T14:30:00.000Z',
        'purchaseAmount' => ['value' => 299.99, 'currency' => Currencies::EUR],
        'service' => 'Premium Software License',
        // ... other sector-specific fields
    ]);
    $kloutitCase->updateCase('CASE_001', $updateBody);
    
    // 4. Check case completeness
    $caseStatus = $kloutitCase->checkCase('CASE_001');
    
    // 5. Submit completed case for defense generation
    if (empty($caseStatus)) {
        $kloutitCase->submitCompletedCase('CASE_001');
    }
    
    // 6. Download defense when ready
    $defense = $kloutitCase->downloadCaseDefense('PDF', 'CASE_001');
    
    echo "Workflow completed successfully!\n";
    
} catch (Exception $e) {
    echo "Workflow error: " . $e->getMessage() . "\n";
    throw $e;
}
```

### Error Handling

The API returns standard HTTP status codes:

- **200** - Success
- **201** - Created successfully
- **204** - No content (successful operation)
- **206** - Partial content (case has non-required fields missing)
- **400** - Bad request (validation errors)
- **401** - Unauthorized (invalid API key)
- **404** - Not found (case doesn't exist)
- **406** - Not acceptable (case has required fields missing)

### Rate Limiting

Please refer to your API key dashboard for rate limiting information and ensure your integration handles rate limits appropriately.

## Documentation

In this document, you will be able to see all the available methods and all the parameters needed, so you know exactly what you need to do. For complete API documentation with detailed parameter specifications, visit the [Kloutit API Reference](https://clients-api.kloutit.com/api).

If you have any doubts, please, don't hesitate to contact us so we can help you, or leave us any comment so we can improve your experience.

## Autocompletion

If you use an IDE such as PhpStorm or VSCode with PHP extensions, you will be able to see all the autocompletion for methods and parameters, so you know exactly what the call is expecting to receive.

## Security

Kloutit SDK uses API key for authentication. It is the responsibility of the SDK consumer to keep the API key secure and not expose it in source code, public repositories, or insecure environments.

To ensure the security of your integration:

- Store the API key in environment variables or a secure secret manager.
- Do not share your API key in public source code or with unauthorized third parties.
- Regularly rotate API keys to minimize exposure risks.

Please, if you discover any security issues, report them to support@kloutit.com as soon as possible.

## License

Apache 2.0

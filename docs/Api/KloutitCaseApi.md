# Kloutit\KloutitCaseApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**checkCase()**](KloutitCaseApi.md#checkCase) | **POST** /case/{expedientNumber}/check-case | Check case information |
| [**submitCompletedCase()**](KloutitCaseApi.md#submitCompletedCase) | **POST** /case/{expedientNumber}/submit-completed-case | Submit completed case |
| [**updateCase()**](KloutitCaseApi.md#updateCase) | **POST** /case/{expedientNumber}/update-case | Update case |
| [**uploadFile()**](KloutitCaseApi.md#uploadFile) | **POST** /case/{expedientNumber}/upload-file | Upload file |
| [**uploadProductPhoto()**](KloutitCaseApi.md#uploadProductPhoto) | **POST** /case/{expedientNumber}/upload-product-photo | Upload product photo |
| [**verifyEvent()**](KloutitCaseApi.md#verifyEvent) | **POST** /case/verify-event | Verify webhook event |


## `checkCase()`

```php
checkCase($expedient_number)
```

Check case information

Validates that the case has been updated with all the needed information. It indicates in the response if there are still some fields that could be informed to Kloutit before generating the dispute. It also informs the type and the required nature of each field.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitCaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$expedient_number = 'expedient_number_example'; // string | Case expedient number. This value must exist in Kloutit.

try {
    $apiInstance->checkCase($expedient_number);
} catch (Exception $e) {
    echo 'Exception when calling KloutitCaseApi->checkCase: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **expedient_number** | **string**| Case expedient number. This value must exist in Kloutit. | |

### Return type

void (empty response body)

### Authorization

[x-api-key](../../README.md#x-api-key)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `submitCompletedCase()`

```php
submitCompletedCase($expedient_number)
```

Submit completed case

Submits that the case has been updated with all the needed information. If you have configured automated dispute generation in Kloutit, this endpoint will indicate that the case is ready and will trigger the defense generation automatically.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitCaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$expedient_number = 'expedient_number_example'; // string | Case expedient number. This value must exist in Kloutit.

try {
    $apiInstance->submitCompletedCase($expedient_number);
} catch (Exception $e) {
    echo 'Exception when calling KloutitCaseApi->submitCompletedCase: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **expedient_number** | **string**| Case expedient number. This value must exist in Kloutit. | |

### Return type

void (empty response body)

### Authorization

[x-api-key](../../README.md#x-api-key)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateCase()`

```php
updateCase($expedient_number, $update_case_params): \Kloutit\Model\ModelCase
```

Update case

Updates data to enrich an existing case in order to generate a more complete defense and increase the chances of winning.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitCaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$expedient_number = 'expedient_number_example'; // string | Case expedient number. This value must exist in Kloutit.
$update_case_params = {"sector":"DIGITAL_PRODUCT","filialIdentifier":"B12345678","transactionDate":"2025-02-12T11:03:43.126Z","bankName":"Sample bank","cardBrand":"Sample card brand","last4Digits":"1234","is3DSPurchase":true,"purchaseDate":"2025-02-12T11:03:43.126Z","purchaseAmount":{"currency":"EUR","value":10},"isChargeRefundable":true,"customerName":"Node SDK sample","customerEmail":"kloutit-node@example.com","customerPhone":"612345678","additionalInfo":"Some optional additional info","communications":[{"sender":"Sender name","content":"Communication content","date":"2025-02-12T11:03:43.126Z"}],"product":"Sample product","service":"Sample service","shippingCity":"Barcelona","shippingProvince":"Barcelona","shippingPostalCode":"08000","deliveryConfirmation":true,"shippingDate":"2025-02-12T11:03:43.126Z","deliveryDate":"2025-02-12T11:03:43.126Z","deliveryCompany":"Sample company"}; // \Kloutit\Model\UpdateCaseParams

try {
    $result = $apiInstance->updateCase($expedient_number, $update_case_params);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KloutitCaseApi->updateCase: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **expedient_number** | **string**| Case expedient number. This value must exist in Kloutit. | |
| **update_case_params** | [**\Kloutit\Model\UpdateCaseParams**](../Model/UpdateCaseParams.md)|  | |

### Return type

[**\Kloutit\Model\ModelCase**](../Model/ModelCase.md)

### Authorization

[x-api-key](../../README.md#x-api-key)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `uploadFile()`

```php
uploadFile($expedient_number, $file, $category): \Kloutit\Model\FileItem
```

Upload file

Uploads a file into an existing case. You need to send a request of type ``multipart/form-data``. Allowed formats are ``PDF``, ``JPG``, ``JPEG``, ``PNG``. Max. file size is ``10Mb``

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitCaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$expedient_number = 'expedient_number_example'; // string
$file = "/path/to/file.txt"; // \SplFileObject | A file to upload. Make sure that the specifications follow RFC 2388, which defines file transfers for the multipart/form-data protocol. Allowed formats are ``PDF``, ``JPG``, ``JPEG``, ``PNG``. Max. file size is ``10Mb``. Ensure that the file upload adheres to [RFC 2388](https://www.ietf.org/rfc/rfc2388.txt), which defines file transfers for the multipart/form-data protocol.
$category = 'category_example'; // string | Category of the file

try {
    $result = $apiInstance->uploadFile($expedient_number, $file, $category);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KloutitCaseApi->uploadFile: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **expedient_number** | **string**|  | |
| **file** | **\SplFileObject****\SplFileObject**| A file to upload. Make sure that the specifications follow RFC 2388, which defines file transfers for the multipart/form-data protocol. Allowed formats are &#x60;&#x60;PDF&#x60;&#x60;, &#x60;&#x60;JPG&#x60;&#x60;, &#x60;&#x60;JPEG&#x60;&#x60;, &#x60;&#x60;PNG&#x60;&#x60;. Max. file size is &#x60;&#x60;10Mb&#x60;&#x60;. Ensure that the file upload adheres to [RFC 2388](https://www.ietf.org/rfc/rfc2388.txt), which defines file transfers for the multipart/form-data protocol. | |
| **category** | **string**| Category of the file | |

### Return type

[**\Kloutit\Model\FileItem**](../Model/FileItem.md)

### Authorization

[x-api-key](../../README.md#x-api-key)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `uploadProductPhoto()`

```php
uploadProductPhoto($expedient_number, $file): \Kloutit\Model\FileItem
```

Upload product photo

Uploads a product file into an existing case. You need to send a request of type ``multipart/form-data``. This file can be attached only for marketplace company. Allowed formats are ``JPG``, ``JPEG``, ``PNG``. Max. file size is ``10Mb``

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitCaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$expedient_number = 'expedient_number_example'; // string
$file = "/path/to/file.txt"; // \SplFileObject | A file to upload. Make sure that the specifications follow RFC 2388, which defines file transfers for the multipart/form-data protocol. Allowed formats are ``JPG``, ``JPEG``, ``PNG``. Max. file size is ``10Mb``. Ensure that the file upload adheres to [RFC 2388](https://www.ietf.org/rfc/rfc2388.txt), which defines file transfers for the multipart/form-data protocol.

try {
    $result = $apiInstance->uploadProductPhoto($expedient_number, $file);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KloutitCaseApi->uploadProductPhoto: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **expedient_number** | **string**|  | |
| **file** | **\SplFileObject****\SplFileObject**| A file to upload. Make sure that the specifications follow RFC 2388, which defines file transfers for the multipart/form-data protocol. Allowed formats are &#x60;&#x60;JPG&#x60;&#x60;, &#x60;&#x60;JPEG&#x60;&#x60;, &#x60;&#x60;PNG&#x60;&#x60;. Max. file size is &#x60;&#x60;10Mb&#x60;&#x60;. Ensure that the file upload adheres to [RFC 2388](https://www.ietf.org/rfc/rfc2388.txt), which defines file transfers for the multipart/form-data protocol. | |

### Return type

[**\Kloutit\Model\FileItem**](../Model/FileItem.md)

### Authorization

[x-api-key](../../README.md#x-api-key)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `verifyEvent()`

```php
verifyEvent($client_webhook_event_dto)
```

Verify webhook event

Verifies if the webhook event received has been sent by Kloutit

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitCaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$client_webhook_event_dto = new \Kloutit\Model\ClientWebhookEventDto(); // \Kloutit\Model\ClientWebhookEventDto

try {
    $apiInstance->verifyEvent($client_webhook_event_dto);
} catch (Exception $e) {
    echo 'Exception when calling KloutitCaseApi->verifyEvent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **client_webhook_event_dto** | [**\Kloutit\Model\ClientWebhookEventDto**](../Model/ClientWebhookEventDto.md)|  | |

### Return type

void (empty response body)

### Authorization

[x-api-key](../../README.md#x-api-key)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

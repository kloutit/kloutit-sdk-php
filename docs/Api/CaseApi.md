# Kloutit\CaseApi

All URIs are relative to https://clients-api.kloutit.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**checkCase()**](CaseApi.md#checkCase) | **POST** /case/{expedientNumber}/check-case | Check case information |
| [**submitCompletedCase()**](CaseApi.md#submitCompletedCase) | **POST** /case/{expedientNumber}/submit-completed-case | Submit completed case |
| [**updateCase()**](CaseApi.md#updateCase) | **POST** /case/{expedientNumber}/update-case | Update case |
| [**uploadFile()**](CaseApi.md#uploadFile) | **POST** /case/{expedientNumber}/upload-file | Upload file |


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


$apiInstance = new Kloutit\Api\CaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$expedient_number = 'expedient_number_example'; // string | Case expedient number. This value must exist in Kloutit.

try {
    $apiInstance->checkCase($expedient_number);
} catch (Exception $e) {
    echo 'Exception when calling CaseApi->checkCase: ', $e->getMessage(), PHP_EOL;
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


$apiInstance = new Kloutit\Api\CaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$expedient_number = 'expedient_number_example'; // string | Case expedient number. This value must exist in Kloutit.

try {
    $apiInstance->submitCompletedCase($expedient_number);
} catch (Exception $e) {
    echo 'Exception when calling CaseApi->submitCompletedCase: ', $e->getMessage(), PHP_EOL;
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


$apiInstance = new Kloutit\Api\CaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$expedient_number = 'expedient_number_example'; // string | Case expedient number. This value must exist in Kloutit.
$update_case_params = {"organizationType":"DIGITAL_PRODUCT","expedientNumber":"EXPNODE0001","notificationDate":"2024-09-22T11:31:22.347Z","deadline":"2027-09-22T11:31:22.347Z","disputeAmount":{"currency":"€","value":10},"chargebackReason":"PRODUCT_SERVICE_NOT_RECEIVED","transactionDate":"2024-09-22T11:31:22.347Z","panNumber":"PAN000001","transactionId":"TR0000001","bankName":"Sample bank","is3DSPurchase":true,"purchaseDate":"2024-09-22T11:31:22.347Z","purchaseAmount":{"currency":"€","value":10},"product":"Sample product","isChargeRefundable":true,"shippingCity":"Barcelona","shippingProvince":"Barcelona","shippingPostalCode":"08000","shippingDate":"2024-09-22T11:31:22.347Z","deliveryCompany":"Sample company","deliveryDate":"2024-09-22T11:31:22.347Z","deliveryConfirmation":true,"customerName":"Node SDK sample","customerEmail":"kloutit-node@example.com","contactDate":"2024-09-22T11:31:22.347Z","customerPhone":"612345678","additionalInfo":"Some optional additional info"}; // \Kloutit\Model\UpdateCaseParams

try {
    $result = $apiInstance->updateCase($expedient_number, $update_case_params);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CaseApi->updateCase: ', $e->getMessage(), PHP_EOL;
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
uploadFile($expedient_number, $file, $type): \Kloutit\Model\FileItem
```

Upload file

Uploads a file into an existing case. You need to send a request of type ``multipart/form-data``. This file can be attached as a customer evidence, company evidence or product related file (for marketplace). Allowed formats are ``PDF``, ``JPG``, ``JPEG``, ``PNG``. Max. file size is ``10Mb``

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\CaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$expedient_number = 'expedient_number_example'; // string
$file = "/path/to/file.txt"; // \SplFileObject | A file to upload. Make sure that the specifications follow RFC 2388, which defines file transfers for the multipart/form-data protocol. Allowed formats are ``PDF``, ``JPG``, ``JPEG``, ``PNG``. Max. file size is ``10Mb``. Ensure that the file upload adheres to [RFC 2388](https://www.ietf.org/rfc/rfc2388.txt), which defines file transfers for the multipart/form-data protocol.
$type = 'type_example'; // string | Type of file: ``customer``, ``company`` or ``product`` (product only for marketplace)

try {
    $result = $apiInstance->uploadFile($expedient_number, $file, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CaseApi->uploadFile: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **expedient_number** | **string**|  | |
| **file** | **\SplFileObject****\SplFileObject**| A file to upload. Make sure that the specifications follow RFC 2388, which defines file transfers for the multipart/form-data protocol. Allowed formats are &#x60;&#x60;PDF&#x60;&#x60;, &#x60;&#x60;JPG&#x60;&#x60;, &#x60;&#x60;JPEG&#x60;&#x60;, &#x60;&#x60;PNG&#x60;&#x60;. Max. file size is &#x60;&#x60;10Mb&#x60;&#x60;. Ensure that the file upload adheres to [RFC 2388](https://www.ietf.org/rfc/rfc2388.txt), which defines file transfers for the multipart/form-data protocol. | |
| **type** | **string**| Type of file: &#x60;&#x60;customer&#x60;&#x60;, &#x60;&#x60;company&#x60;&#x60; or &#x60;&#x60;product&#x60;&#x60; (product only for marketplace) | |

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

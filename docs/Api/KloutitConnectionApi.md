# Kloutit\KloutitConnectionApi

All URIs are relative to https://clients-api.kloutit.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getConnectionInfo()**](KloutitConnectionApi.md#getConnectionInfo) | **GET** /connection | Get connection info |


## `getConnectionInfo()`

```php
getConnectionInfo(): \Kloutit\Model\ConnectionInfoDto
```

Get connection info

Checks that the API Key sent in the x-api-key header is valid and returns the public info (name and sectors) of the organization it belongs to. Returns a 200 response when the key is valid and a 401 response otherwise.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitConnectionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getConnectionInfo();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KloutitConnectionApi->getConnectionInfo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Kloutit\Model\ConnectionInfoDto**](../Model/ConnectionInfoDto.md)

### Authorization

[x-api-key](../../README.md#x-api-key)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

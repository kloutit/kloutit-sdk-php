# Kloutit\KloutitCaseApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCase()**](KloutitCaseApi.md#createCase) | **POST** /case | Create a new case into Kloutit. |


## `createCase()`

```php
createCase($kloutit_case_body): \Kloutit\Model\KloutitCaseResponse
```

Create a new case into Kloutit.

Case SDK call to create a new chargeback case from your system into Kloutit. Authentication header `Bearer {token}` is needed, where the token has been retrieved using the login API.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (JWT) authorization: bearer
$config = Kloutit\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new Kloutit\Api\KloutitCaseApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$kloutit_case_body = new \Kloutit\Model\KloutitCaseBody(); // \Kloutit\Model\KloutitCaseBody

try {
    $result = $apiInstance->createCase($kloutit_case_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KloutitCaseApi->createCase: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **kloutit_case_body** | [**\Kloutit\Model\KloutitCaseBody**](../Model/KloutitCaseBody.md)|  | |

### Return type

[**\Kloutit\Model\KloutitCaseResponse**](../Model/KloutitCaseResponse.md)

### Authorization

[bearer](../../README.md#bearer)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

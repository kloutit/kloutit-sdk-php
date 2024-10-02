# Kloutit\KloutitLoginApi

All URIs are relative to http://localhost, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**login()**](KloutitLoginApi.md#login) | **POST** /clients/{organizationId}/login | Get access token. |


## `login()`

```php
login($organization_id, $kloutit_login_body): \Kloutit\Model\KloutitLoginResponse
```

Get access token.

Login SDK call to get an access token that could be used for other calls that need bearer authentication. We strongly recommend to store the retrieved access token into some cache, so it would not be generated on each call. The token can be used as many times as you want until is not expires. Then a new one must be generated. Authentication header `Basic {token}` is needed, where basic token is generated in base64 using `{clientId}:{clientSecret}`

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure HTTP basic authorization: basic
$config = Kloutit\Configuration::getDefaultConfiguration()
              ->setUsername('YOUR_USERNAME')
              ->setPassword('YOUR_PASSWORD');


$apiInstance = new Kloutit\Api\KloutitLoginApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$organization_id = 'organization_id_example'; // string | Organization id
$kloutit_login_body = new \Kloutit\Model\KloutitLoginBody(); // \Kloutit\Model\KloutitLoginBody

try {
    $result = $apiInstance->login($organization_id, $kloutit_login_body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KloutitLoginApi->login: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **organization_id** | **string**| Organization id | |
| **kloutit_login_body** | [**\Kloutit\Model\KloutitLoginBody**](../Model/KloutitLoginBody.md)|  | |

### Return type

[**\Kloutit\Model\KloutitLoginResponse**](../Model/KloutitLoginResponse.md)

### Authorization

[basic](../../README.md#basic)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

# Kloutit\KloutitWebhooksApi

All URIs are relative to https://clients-api.kloutit.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listWebhooks()**](KloutitWebhooksApi.md#listWebhooks) | **GET** /webhooks | List webhook subscriptions |
| [**subscribeWebhook()**](KloutitWebhooksApi.md#subscribeWebhook) | **POST** /webhooks | Subscribe a webhook |
| [**unsubscribeWebhook()**](KloutitWebhooksApi.md#unsubscribeWebhook) | **DELETE** /webhooks/{id} | Unsubscribe a webhook |


## `listWebhooks()`

```php
listWebhooks(): \Kloutit\Model\WebhookSubscriptionDto[]
```

List webhook subscriptions

Returns the webhook subscriptions registered with the API key making the call.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitWebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listWebhooks();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KloutitWebhooksApi->listWebhooks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\Kloutit\Model\WebhookSubscriptionDto[]**](../Model/WebhookSubscriptionDto.md)

### Authorization

[x-api-key](../../README.md#x-api-key)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `subscribeWebhook()`

```php
subscribeWebhook($subscribe_webhook_dto): \Kloutit\Model\WebhookSubscriptionDto
```

Subscribe a webhook

Registers a URL Kloutit will POST events to. The subscription is tied to the API key making the call. Returns the created subscription, including the id used to unsubscribe later. Subscribing the same URL for the same event twice returns the existing subscription.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitWebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$subscribe_webhook_dto = new \Kloutit\Model\SubscribeWebhookDto(); // \Kloutit\Model\SubscribeWebhookDto

try {
    $result = $apiInstance->subscribeWebhook($subscribe_webhook_dto);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling KloutitWebhooksApi->subscribeWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **subscribe_webhook_dto** | [**\Kloutit\Model\SubscribeWebhookDto**](../Model/SubscribeWebhookDto.md)|  | |

### Return type

[**\Kloutit\Model\WebhookSubscriptionDto**](../Model/WebhookSubscriptionDto.md)

### Authorization

[x-api-key](../../README.md#x-api-key)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `unsubscribeWebhook()`

```php
unsubscribeWebhook($id)
```

Unsubscribe a webhook

Removes a webhook subscription by id. Idempotent: removing an unknown subscription succeeds with no effect.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: x-api-key
$config = Kloutit\Configuration::getDefaultConfiguration()->setApiKey('x-api-key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Kloutit\Configuration::getDefaultConfiguration()->setApiKeyPrefix('x-api-key', 'Bearer');


$apiInstance = new Kloutit\Api\KloutitWebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 'id_example'; // string

try {
    $apiInstance->unsubscribeWebhook($id);
} catch (Exception $e) {
    echo 'Exception when calling KloutitWebhooksApi->unsubscribeWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **string**|  | |

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

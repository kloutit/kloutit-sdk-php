# # WebhookSubscriptionDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique id of the subscription. Store it to unsubscribe later. |
**target_url** | **string** | The URL Kloutit POSTs events to. |
**event** | [**\Kloutit\Model\WebhookEventType**](WebhookEventType.md) | Event type this subscription receives, if scoped. | [optional]
**created_at** | **\DateTime** | When the subscription was created. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)

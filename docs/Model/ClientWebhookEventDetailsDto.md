# # ClientWebhookEventDetailsDto

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**sector** | **string** | Case sector | [optional]
**chargeback_reason** | **string** | Chargeback reason reported by the payment processor | [optional]
**deadline** | **\DateTime** | Deadline to submit the dispute response | [optional]
**order_number** | **string** | Merchant&#39;s order number, when the payment processor reports it | [optional]
**transaction_id** | **string** | PSP transaction id | [optional]
**transaction_date** | **\DateTime** |  | [optional]
**bank_name** | **string** |  | [optional]
**card_brand** | **string** |  | [optional]
**last4_digits** | **string** |  | [optional]
**is3_ds_purchase** | **bool** |  | [optional]
**dispute_amount** | [**\Kloutit\Model\WebhookEventAmountDto**](WebhookEventAmountDto.md) |  | [optional]
**purchase_date** | **\DateTime** |  | [optional]
**purchase_amount** | [**\Kloutit\Model\WebhookEventAmountDto**](WebhookEventAmountDto.md) |  | [optional]
**is_charge_refundable** | **bool** |  | [optional]
**customer_name** | **string** |  | [optional]
**customer_email** | **string** |  | [optional]
**customer_phone** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)

# # ModelCase

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  | [optional] [readonly]
**active** | **bool** |  | [optional] [readonly] [default to true]
**created_at** | **\DateTime** |  | [optional] [readonly]
**updated_at** | **\DateTime** |  | [optional] [readonly]
**is_deleted** | **bool** |  | [optional] [readonly] [default to false]
**deleted_at** | **\DateTime** |  | [optional] [readonly]
**status** | [**\Kloutit\Model\CaseStatus**](CaseStatus.md) |  |
**sales_channel_code** | **string** | The sales channel code related to the case. | [optional]
**filial_identifier** | **string** | Filial identifier related to the case. | [optional]
**payment_processor** | **string** |  | [optional] [readonly]
**purchase_date** | **\DateTime** | Date when the customer made the purchase in UTC and ISO 8601 format. |
**service** | **string** | Service that the customer bought. | [optional]
**product** | **string** | Product that the customer bought. | [optional]
**is_charge_refundable** | **bool** | Flag that indicates if the charge made is refundable regarding your company terms and conditions. |
**customer_name** | **string** | Customer name. | [optional]
**customer_email** | **string** | Customer email | [optional]
**customer_phone** | **string** | Customer phone. | [optional]
**service_date** | **\DateTime** | Date when the service was provided or will be provided in UTC and ISO 8601 format. | [optional]
**service_was_provided** | **bool** | Flag that indicates if the service was provided or not. | [optional]
**checkin_date** | **\DateTime** | Check in date in UTC and ISO 8601 format. | [optional]
**checkout_date** | **\DateTime** | Check out date in UTC and ISO 8601 format. | [optional]
**hotel_name** | **string** | Hotel name. | [optional]
**rate** | **string** | Rate applied. | [optional]
**inbound_rate** | **string** | Rate applied in return trip. | [optional]
**checkin_confirmation** | **bool** | Flag that indicates if the client made the checkin or not. | [optional]
**departure_country** | **string** | Departure country. | [optional]
**destination_country** | **string** | Destination country. | [optional]
**departure_date** | **\DateTime** | Departure date in UTC and ISO 8601 format. | [optional]
**arrival_date** | **\DateTime** | Arrival date in UTC and ISO 8601 format. | [optional]
**inbound_departure_country** | **string** | Departure country of return trip. | [optional]
**inbound_destination_country** | **string** | Destination country of return trip. | [optional]
**inbound_departure_date** | **\DateTime** | Departure date of return trip in UTC and ISO 8601 format. | [optional]
**inbound_arrival_date** | **\DateTime** | Arrival date of return trip in UTC and ISO 8601 format. | [optional]
**departure_airport** | **string** | Departure airport. | [optional]
**arrival_airport** | **string** | Arrival airport. | [optional]
**departure_city** | **string** | Departure city. | [optional]
**arrival_city** | **string** | Arrival city. | [optional]
**inbound_departure_city** | **string** | Departure city of return trip. | [optional]
**inbound_arrival_city** | **string** | Arrival city of return trip. | [optional]
**shipping_city** | **string** | Shipping city. | [optional]
**shipping_province** | **string** | Shipping province. | [optional]
**shipping_postal_code** | **string** | Shipping postal code. | [optional]
**shipping_date** | **\DateTime** | Shipping date in UTC and ISO 8601 format. | [optional]
**delivery_date** | **\DateTime** | Delivery date in UTC and ISO 8601 format. | [optional]
**delivery_company** | **string** | Delivery company. | [optional]
**delivery_confirmation** | **bool** | Flag that indicates if the customer received the product. | [optional]
**commitment_start_date** | **\DateTime** | Start date in UTC and ISO 8601 format of the commitment that the customer has with the company. | [optional]
**commitment_end_date** | **\DateTime** | End date in UTC and ISO 8601 format of the commitment that the customer has with the company. | [optional]
**is_cancelled** | **bool** | Flag that indicates if the subscription is cancelled or active. | [optional]
**product_description** | **string** | Product description. | [optional]
**expedient_number** | **string** | Chargeback expedient number. | [readonly]
**notification_date** | **\DateTime** | Chargeback notification date, when the merchant receives the chargeback notification, in UTC and ISO 8601 format. | [readonly]
**dispute_amount** | [**\Kloutit\Model\CaseDisputeAmount**](CaseDisputeAmount.md) |  |
**chargeback_reason** | [**\Kloutit\Model\ChargebackReason**](ChargebackReason.md) |  |
**deadline** | **\DateTime** | Deadline date to resolve this chargeback in UTC and ISO 8601 format. | [optional] [readonly]
**contact_date** | **\DateTime** | Date when the customer contacted to the merchant in UTC and ISO 8601 format. | [optional]
**communications** | [**\Kloutit\Model\CommunicationItem[]**](CommunicationItem.md) | Array of all the emails that the customer has sent regarding this dispute. The structure of each item contains: **sender**: *customer* or *company*, **date**, **content**: string containing the message | [optional]
**additional_info** | **string** | Additional info related to the chargeback. | [optional]
**last4_digits** | **string** | Last 4 digits of the customer&#39;s credit card number. | [optional]
**transaction_id** | **string** | Transaction id. | [optional] [readonly]
**transaction_date** | **\DateTime** | Transaction date in UTC and ISO 8601 format. |
**purchase_amount** | [**\Kloutit\Model\Amount**](Amount.md) | Purchase amount. |
**bank_name** | **string** | Customer bank name. | [optional]
**card_brand** | **string** | Card brand that the customer used to make the payment. | [optional]
**is3_ds_purchase** | **bool** | Flag that indicates if the purchase has been made with 3DS. | [optional]
**sector** | **string** | Organization sector of the case. | [optional]
**seller_contact_date** | **\DateTime** | Date when the customer contacted to the seller in UTC and ISO 8601 format. | [optional]
**seller_additional_info** | **string** | Seller additional infromation. | [optional]
**seller_name** | **string** | Seller name. | [optional]
**seller_phone** | **string** | Seller phone number. | [optional]
**seller_email** | **string** | Seller email. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)

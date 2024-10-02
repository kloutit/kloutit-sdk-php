# # KloutitCaseBody

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** |  | [optional] [readonly]
**active** | **bool** |  | [optional] [readonly] [default to true]
**created_at** | **\DateTime** |  | [optional] [readonly]
**updated_at** | **\DateTime** |  | [optional] [readonly]
**is_deleted** | **bool** |  | [optional] [readonly] [default to false]
**deleted_at** | **\DateTime** |  | [optional] [readonly]
**purchase_date** | **\DateTime** | Date when the customer made the purchase. |
**service** | **string** | Service that the customer bought. | [optional]
**product** | **string** | Product that the customer bought. | [optional]
**is_charge_refundable** | **bool** | Flag that indicates if the charge made is refundable regarding your company terms and conditions. |
**customer_name** | **string** | Customer name. |
**customer_email** | **string** | Customer email |
**customer_phone** | **string** | Customer phone. | [optional]
**service_date** | **\DateTime** | Date when the serve was provided or will be provided. | [optional]
**service_was_provided** | **bool** | Flag that indicates if the service was provided or not. | [optional]
**checkin_date** | **\DateTime** | Check in date. | [optional]
**checkout_date** | **\DateTime** | Check out date. | [optional]
**hotel_name** | **string** | Hotel name. | [optional]
**rate** | **string** | Rate applied. | [optional]
**checkin_confirmation** | **bool** | Flag that indicates if the client made the checkin or not. | [optional]
**destination_country** | **string** | Destination country. | [optional]
**departure_date** | **\DateTime** | Departure date. | [optional]
**arrival_date** | **\DateTime** | Arrival date. | [optional]
**departure_airport** | **string** | Departure airport. | [optional]
**arrival_airport** | **string** | Arrival airport. | [optional]
**shipping_city** | **string** | Shipping city. | [optional]
**shipping_province** | **string** | Shipping province. | [optional]
**shipping_postal_code** | **string** | Shipping postal code. | [optional]
**shipping_date** | **\DateTime** | Shipping date. | [optional]
**delivery_date** | **\DateTime** | Delivery date. | [optional]
**delivery_company** | **string** | Delivery company. | [optional]
**delivery_confirmation** | **bool** | Flag that indicates if the customer received the product. | [optional]
**commitment_start_date** | **\DateTime** | Start date of the commitment that the customer has with the company. | [optional]
**commitment_end_date** | **\DateTime** | End date of the commitment that the customer has with the company. | [optional]
**expedient_number** | **string** | Chargeback expedient number. |
**notification_date** | **\DateTime** | Chargeback notification date, when the merchant receives the chargeback notification. |
**dispute_amount** | [**\Kloutit\Model\AmountDto**](AmountDto.md) | Amount that the customer claims. |
**chargeback_reason** | **string** | Reason why the customer is requesting the chargeback. |
**deadline** | **\DateTime** | Deadline date to resolve this chargeback. | [optional]
**contact_date** | **\DateTime** | Date when the customer contacted to the merchant. | [optional]
**communications** | [**\Kloutit\Model\CommunicationItemDto[]**](CommunicationItemDto.md) | Array of all the emails that the customer has sent regarding this dispute. | [optional]
**additional_info** | **string** | Additional info related to the chargeback. | [optional]
**pan_number** | **string** | Holder credit card number. | [optional]
**transaction_id** | **string** | Transaction id. | [optional]
**transaction_date** | **\DateTime** | Transaction date. |
**purchase_amount** | [**\Kloutit\Model\AmountDto**](AmountDto.md) | Purchase amount. |
**bank_name** | **string** | Customer bank name. | [optional]
**card_brand** | **string** | Card brand that the customer used to make the payment. | [optional]
**is3_ds_purchase** | **bool** | Flag that indicates if the purchase has been made with 3DS. |
**dispute** | **object** |  | [optional]
**organization_id** | **string** | Your organization id. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)

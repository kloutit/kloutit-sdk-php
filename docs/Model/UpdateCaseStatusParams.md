# # UpdateCaseStatusParams

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | [**\Kloutit\Model\CaseResolutionStatus**](CaseResolutionStatus.md) | New status of the case. &#x60;&#x60;ALLEGED&#x60;&#x60;: you have sent the generated defense to the payment processor yourself (only from &#x60;&#x60;GENERATED&#x60;&#x60;). &#x60;&#x60;ACCEPTED&#x60;&#x60;: you accept the chargeback and stop defending the case (from &#x60;&#x60;PENDING&#x60;&#x60;, &#x60;&#x60;GENERATED&#x60;&#x60;, &#x60;&#x60;ALLEGED&#x60;&#x60;, &#x60;&#x60;REOPENED&#x60;&#x60;, &#x60;&#x60;PREARBITRATION&#x60;&#x60; or &#x60;&#x60;ARBITRATION&#x60;&#x60;). &#x60;&#x60;WON&#x60;&#x60; / &#x60;&#x60;LOST&#x60;&#x60;: outcome of the case once its defense has been sent (only from &#x60;&#x60;ALLEGED&#x60;&#x60;). A resolved case cannot change its status again. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)

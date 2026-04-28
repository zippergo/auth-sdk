

# MerchantSummary

Summary view of a merchant including business info, status, and onboarding origin

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** | Unique identifier of the merchant |  [optional] |
|**businessName** | **String** | Registered business name of the merchant |  [optional] |
|**email** | **String** | Email address associated with the merchant account |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Current account status of the merchant |  [optional] |
|**origin** | [**OriginEnum**](#OriginEnum) | How the merchant was onboarded (e.g. SELF, PARTNER) |  [optional] |
|**partnerId** | **UUID** | Identifier of the partner that onboarded this merchant, if any |  [optional] |
|**createdAt** | **OffsetDateTime** | Timestamp when the merchant was created |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING_ACTIVATION | &quot;PENDING_ACTIVATION&quot; |
| PENDING_PASSWORD_SETUP | &quot;PENDING_PASSWORD_SETUP&quot; |
| ACTIVE | &quot;ACTIVE&quot; |
| SUSPENDED | &quot;SUSPENDED&quot; |



## Enum: OriginEnum

| Name | Value |
|---- | -----|
| SELF | &quot;SELF&quot; |
| PARTNER_API | &quot;PARTNER_API&quot; |
| ADMIN | &quot;ADMIN&quot; |




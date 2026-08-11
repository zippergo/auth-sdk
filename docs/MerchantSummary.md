

# MerchantSummary

Summary view of a merchant including business info, status, and onboarding origin

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** | Unique identifier of the merchant |  [optional] |
|**businessName** | **String** | Registered business name of the merchant |  [optional] |
|**nameHe** | **String** | Hebrew business name |  [optional] |
|**nameEn** | **String** | English business name |  [optional] |
|**ownerHe** | **String** | Owner full name (Hebrew display) |  [optional] |
|**ownerEn** | **String** | Owner full name (English display) |  [optional] |
|**businessType** | [**BusinessTypeEnum**](#BusinessTypeEnum) | Business category |  [optional] |
|**email** | **String** | Email address associated with the merchant account |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Current account status of the merchant |  [optional] |
|**origin** | [**OriginEnum**](#OriginEnum) | How the merchant was onboarded (e.g. SELF, PARTNER) |  [optional] |
|**partnerId** | **UUID** | Identifier of the partner that onboarded this merchant, if any |  [optional] |
|**referralCode** | **String** | Referral code generated for this merchant |  [optional] |
|**referrerUserId** | **UUID** | User id of the referrer (partner&#39;s user id) when onboarded by a partner |  [optional] |
|**createdAt** | **OffsetDateTime** | Timestamp when the merchant was created |  [optional] |



## Enum: BusinessTypeEnum

| Name | Value |
|---- | -----|
| FOOD | &quot;food&quot; |
| RETAIL | &quot;retail&quot; |



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
| SSO | &quot;SSO&quot; |




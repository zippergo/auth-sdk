

# MerchantDetail

Full merchant profile for the detail view

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** | Unique identifier of the merchant |  [optional] |
|**nameHe** | **String** | Hebrew business name |  [optional] |
|**nameEn** | **String** | English business name |  [optional] |
|**businessName** | **String** | Legacy/canonical business name |  [optional] |
|**ownerHe** | **String** | Owner full name (Hebrew display) |  [optional] |
|**ownerEn** | **String** | Owner full name (English display) |  [optional] |
|**email** | **String** | Owner account email |  [optional] |
|**businessEmail** | **String** | Public-facing business email |  [optional] |
|**businessPhone** | **String** | Business phone |  [optional] |
|**businessType** | [**BusinessTypeEnum**](#BusinessTypeEnum) | Business category |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Account status (active/suspended/pending derived client-side) |  [optional] |
|**origin** | [**OriginEnum**](#OriginEnum) | How the merchant was onboarded |  [optional] |
|**partnerId** | **UUID** | Owning partner id, if any |  [optional] |
|**referralCode** | **String** | Merchant referral code |  [optional] |
|**referrerUserId** | **UUID** | Referrer (partner) user id, if any |  [optional] |
|**addressHe** | **String** | Hebrew address line |  [optional] |
|**addressEn** | **String** | English address line |  [optional] |
|**cityHe** | **String** | Hebrew city |  [optional] |
|**cityEn** | **String** | English city |  [optional] |
|**lat** | **Double** | Latitude |  [optional] |
|**lng** | **Double** | Longitude |  [optional] |
|**createdAt** | **OffsetDateTime** | Creation timestamp |  [optional] |
|**lastModifiedAt** | **OffsetDateTime** | Last modification timestamp |  [optional] |



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




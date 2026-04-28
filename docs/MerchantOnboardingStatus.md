

# MerchantOnboardingStatus

Current onboarding status of a merchant including verification state

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**merchantId** | **UUID** | Unique identifier of the merchant |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Current account status of the merchant |  [optional] |
|**emailVerified** | **Boolean** | Whether the merchant&#39;s email address has been verified |  [optional] |
|**createdAt** | **OffsetDateTime** | Timestamp when the merchant was created |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING_ACTIVATION | &quot;PENDING_ACTIVATION&quot; |
| PENDING_PASSWORD_SETUP | &quot;PENDING_PASSWORD_SETUP&quot; |
| ACTIVE | &quot;ACTIVE&quot; |
| SUSPENDED | &quot;SUSPENDED&quot; |




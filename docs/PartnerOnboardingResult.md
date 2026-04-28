

# PartnerOnboardingResult

Result of a partner-initiated merchant onboarding, including generated API credentials

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**merchantId** | **UUID** | Unique identifier of the newly onboarded merchant |  [optional] |
|**apiKey** | **String** | Generated API key for the merchant |  [optional] |
|**apiSecret** | **String** | Generated API secret for the merchant – only returned once at creation time |  [optional] |
|**message** | **String** | Human-readable status message about the onboarding result |  [optional] |




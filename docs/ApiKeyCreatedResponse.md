

# ApiKeyCreatedResponse

Response returned when a new API key is created, including the secret shown only once

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** | Unique identifier of the API key |  [optional] |
|**apiKey** | **String** | The API key value used as the client ID |  [optional] |
|**apiSecret** | **String** | The API secret – only returned once at creation time and cannot be retrieved later |  [optional] |
|**label** | **String** | Human-readable label for identifying this API key |  [optional] |
|**scopes** | **Set&lt;String&gt;** | Set of permission scopes granted to this API key |  [optional] |




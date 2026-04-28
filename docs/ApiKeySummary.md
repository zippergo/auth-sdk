

# ApiKeySummary

Summary of an API key including status and usage metadata

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** | Unique identifier of the API key |  [optional] |
|**apiKeyPrefix** | **String** | First few characters of the API key for identification |  [optional] |
|**label** | **String** | Human-readable label for identifying this API key |  [optional] |
|**scopes** | **Set&lt;String&gt;** | Set of permission scopes granted to this API key |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Current status of the API key (e.g. ACTIVE, REVOKED) |  [optional] |
|**createdAt** | **OffsetDateTime** | Timestamp when the API key was created |  [optional] |
|**lastUsedAt** | **OffsetDateTime** | Timestamp when the API key was last used for authentication |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;ACTIVE&quot; |
| REVOKED | &quot;REVOKED&quot; |




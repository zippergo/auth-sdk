

# MerchantBulkStatusRequest

Bulk status change for a set of the partner's merchants

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**merchantIds** | **List&lt;UUID&gt;** | Merchant ids to update |  |
|**action** | [**ActionEnum**](#ActionEnum) | Status action to apply to each merchant |  |



## Enum: ActionEnum

| Name | Value |
|---- | -----|
| ACTIVATE | &quot;ACTIVATE&quot; |
| SUSPEND | &quot;SUSPEND&quot; |




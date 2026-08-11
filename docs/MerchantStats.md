

# MerchantStats

Active-merchant statistics for the authenticated partner

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**active** | **Long** | Number of currently active merchants for this partner |  [optional] |
|**previousActive** | **Long** | Active merchants created before the previous-period cutoff (~30 days ago); used as the comparison base for the period-over-period delta |  [optional] |
|**series** | [**List&lt;Point&gt;**](Point.md) | Cumulative active-merchant count per day for the last 7 days, oldest first |  [optional] |






# SearchMerchantsRequest

Advanced search request for a partner's merchants with filtering, sorting, and pagination. **Query Fields** (full-text, case-insensitive LIKE): `nameEn`, `nameHe`, `businessName`, and the owner's account email. **Available Filter/Sort Fields:** - `businessType` (food | retail, sortable) - `origin` (SELF | PARTNER_API | ADMIN, sortable) - `businessName` (String, sortable) - `createdDate` (Instant, sortable)  Note: account `status` lives on the linked user, so it isn't a mapped field here. Status *filtering* is applied server-side as a join predicate in MerchantQueryService; status *sorting* is not a server-side field and stays client-side. 

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**query** | **String** | Full-text search query string. Matches against predefined query fields using case-insensitive LIKE. |  [optional] |
|**filters** | **Map&lt;String, List&lt;Filter&gt;&gt;** | Filter groups with AND/OR logic. Each group contains a list of filter criteria that are combined using the specified operator. |  [optional] |
|**sort** | [**List&lt;SortField&gt;**](SortField.md) | Sort criteria applied in order. Only sortable fields are accepted. |  [optional] |
|**pagination** | [**Pagination**](Pagination.md) | Pagination parameters. Page numbers are 1-based. |  [optional] |




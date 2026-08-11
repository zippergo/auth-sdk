# PartnerMerchantsApi

All URIs are relative to *http://localhost:8080*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**activatePartnerMerchant**](PartnerMerchantsApi.md#activatePartnerMerchant) | **POST** /auth/partners/merchants/{merchantId}/activate | Activate merchant |
| [**bulkSetPartnerMerchantStatus**](PartnerMerchantsApi.md#bulkSetPartnerMerchantStatus) | **POST** /auth/partners/merchants/bulk/status | Bulk merchant status change |
| [**getPartnerMerchant**](PartnerMerchantsApi.md#getPartnerMerchant) | **GET** /auth/partners/merchants/{merchantId} | Get merchant detail |
| [**getPartnerMerchantByEmail**](PartnerMerchantsApi.md#getPartnerMerchantByEmail) | **GET** /auth/partners/merchants/by-email | Get merchant by email |
| [**getPartnerMerchantDeliveries**](PartnerMerchantsApi.md#getPartnerMerchantDeliveries) | **GET** /auth/partners/merchants/{merchantId}/deliveries | List a merchant&#39;s deliveries |
| [**getPartnerMerchantEarnings**](PartnerMerchantsApi.md#getPartnerMerchantEarnings) | **GET** /auth/partners/merchants/{merchantId}/earnings | List a merchant&#39;s earnings |
| [**getPartnerMerchantEarningsSummary**](PartnerMerchantsApi.md#getPartnerMerchantEarningsSummary) | **GET** /auth/partners/merchants/{merchantId}/earnings/summary | Merchant earnings totals |
| [**getPartnerMerchantStats**](PartnerMerchantsApi.md#getPartnerMerchantStats) | **GET** /auth/partners/merchants/stats | Get active-merchant statistics |
| [**getPartnerMerchantStatus**](PartnerMerchantsApi.md#getPartnerMerchantStatus) | **GET** /auth/partners/merchants/{merchantId}/status | Get merchant onboarding status |
| [**listPartnerMerchants**](PartnerMerchantsApi.md#listPartnerMerchants) | **GET** /auth/partners/merchants | List partner merchants |
| [**partnerOnboardMerchant**](PartnerMerchantsApi.md#partnerOnboardMerchant) | **POST** /auth/partners/merchants | Onboard a new merchant |
| [**searchPartnerMerchants**](PartnerMerchantsApi.md#searchPartnerMerchants) | **POST** /auth/partners/merchants/search | Search partner merchants |
| [**suspendPartnerMerchant**](PartnerMerchantsApi.md#suspendPartnerMerchant) | **POST** /auth/partners/merchants/{merchantId}/suspend | Suspend merchant |
| [**updatePartnerMerchant**](PartnerMerchantsApi.md#updatePartnerMerchant) | **PUT** /auth/partners/merchants/{merchantId} | Update merchant profile |


<a id="activatePartnerMerchant"></a>
# **activatePartnerMerchant**
> MerchantDetail activatePartnerMerchant(merchantId, acceptLanguage)

Activate merchant

Sets the merchant&#39;s account status to ACTIVE. Partner-scoped (404 if not owned).

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    UUID merchantId = UUID.randomUUID(); // UUID | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantDetail result = apiInstance.activatePartnerMerchant(merchantId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#activatePartnerMerchant");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **UUID**|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantDetail**](MerchantDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="bulkSetPartnerMerchantStatus"></a>
# **bulkSetPartnerMerchantStatus**
> MerchantBulkStatusResult bulkSetPartnerMerchantStatus(merchantBulkStatusRequest, acceptLanguage)

Bulk merchant status change

Applies an activate/suspend action to a set of the partner&#39;s merchants. Ids not owned by the partner are silently skipped.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    MerchantBulkStatusRequest merchantBulkStatusRequest = new MerchantBulkStatusRequest(); // MerchantBulkStatusRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantBulkStatusResult result = apiInstance.bulkSetPartnerMerchantStatus(merchantBulkStatusRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#bulkSetPartnerMerchantStatus");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantBulkStatusRequest** | [**MerchantBulkStatusRequest**](MerchantBulkStatusRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantBulkStatusResult**](MerchantBulkStatusResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="getPartnerMerchant"></a>
# **getPartnerMerchant**
> MerchantDetail getPartnerMerchant(merchantId, acceptLanguage)

Get merchant detail

Returns the full profile of one of the authenticated partner&#39;s merchants. Returns 404 if the merchant does not belong to this partner.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    UUID merchantId = UUID.randomUUID(); // UUID | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantDetail result = apiInstance.getPartnerMerchant(merchantId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#getPartnerMerchant");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **UUID**|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantDetail**](MerchantDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="getPartnerMerchantByEmail"></a>
# **getPartnerMerchantByEmail**
> MerchantSummary getPartnerMerchantByEmail(email, acceptLanguage)

Get merchant by email

Looks up a merchant by their email address within the authenticated partner&#39;s scope. Returns the merchant summary if found and belongs to this partner.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    String email = "email_example"; // String | Merchant email address
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantSummary result = apiInstance.getPartnerMerchantByEmail(email, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#getPartnerMerchantByEmail");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **email** | **String**| Merchant email address | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantSummary**](MerchantSummary.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Merchant found |  -  |
| **401** | Unauthorized |  -  |
| **404** | Merchant not found for this partner |  -  |

<a id="getPartnerMerchantDeliveries"></a>
# **getPartnerMerchantDeliveries**
> PageResponseListMerchantDeliveryRow getPartnerMerchantDeliveries(merchantId, page, size, acceptLanguage)

List a merchant&#39;s deliveries

Returns a page of the merchant&#39;s deliveries (newest first) for the detail-page Deliveries tab. Proxied to delivery-hub with a service token; partner-scoped (404 if not owned).

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    UUID merchantId = UUID.randomUUID(); // UUID | 
    Integer page = 1; // Integer | 
    Integer size = 20; // Integer | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListMerchantDeliveryRow result = apiInstance.getPartnerMerchantDeliveries(merchantId, page, size, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#getPartnerMerchantDeliveries");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **UUID**|  | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **size** | **Integer**|  | [optional] [default to 20] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PageResponseListMerchantDeliveryRow**](PageResponseListMerchantDeliveryRow.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="getPartnerMerchantEarnings"></a>
# **getPartnerMerchantEarnings**
> PageResponseListMerchantEarningRow getPartnerMerchantEarnings(merchantId, page, size, acceptLanguage)

List a merchant&#39;s earnings

Returns a page of the merchant&#39;s earnings (credit accruals, newest first) for the detail-page Earnings tab. Proxied to partner-program; partner-scoped (404 if not owned).

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    UUID merchantId = UUID.randomUUID(); // UUID | 
    Integer page = 1; // Integer | 
    Integer size = 20; // Integer | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListMerchantEarningRow result = apiInstance.getPartnerMerchantEarnings(merchantId, page, size, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#getPartnerMerchantEarnings");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **UUID**|  | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **size** | **Integer**|  | [optional] [default to 20] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PageResponseListMerchantEarningRow**](PageResponseListMerchantEarningRow.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="getPartnerMerchantEarningsSummary"></a>
# **getPartnerMerchantEarningsSummary**
> MerchantEarningsSummary getPartnerMerchantEarningsSummary(merchantId, currency, acceptLanguage)

Merchant earnings totals

Lifetime + pending earnings totals for the detail-page stat tiles. Proxied to partner-program; partner-scoped (404 if not owned).

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    UUID merchantId = UUID.randomUUID(); // UUID | 
    String currency = "ILS"; // String | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantEarningsSummary result = apiInstance.getPartnerMerchantEarningsSummary(merchantId, currency, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#getPartnerMerchantEarningsSummary");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **UUID**|  | |
| **currency** | **String**|  | [optional] [default to ILS] |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantEarningsSummary**](MerchantEarningsSummary.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="getPartnerMerchantStats"></a>
# **getPartnerMerchantStats**
> MerchantStats getPartnerMerchantStats(acceptLanguage)

Get active-merchant statistics

Returns active-merchant statistics for the authenticated partner: the current active-merchant count, the active count as of ~30 days ago (the previous-period comparison base), and a 7-day cumulative series for trend display.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantStats result = apiInstance.getPartnerMerchantStats(acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#getPartnerMerchantStats");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantStats**](MerchantStats.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Statistics retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Partner not found |  -  |

<a id="getPartnerMerchantStatus"></a>
# **getPartnerMerchantStatus**
> MerchantOnboardingStatus getPartnerMerchantStatus(merchantId, acceptLanguage)

Get merchant onboarding status

Returns the onboarding status of a specific merchant, including account status, email verification state, and creation date. The merchant must belong to the authenticated partner.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    UUID merchantId = UUID.randomUUID(); // UUID | Merchant identifier
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantOnboardingStatus result = apiInstance.getPartnerMerchantStatus(merchantId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#getPartnerMerchantStatus");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **UUID**| Merchant identifier | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantOnboardingStatus**](MerchantOnboardingStatus.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Merchant status retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden – merchant does not belong to this partner |  -  |
| **404** | Merchant not found |  -  |

<a id="listPartnerMerchants"></a>
# **listPartnerMerchants**
> MerchantSummary listPartnerMerchants(pageable, acceptLanguage)

List partner merchants

Returns a paginated list of all merchants onboarded by the authenticated partner, including their business name, email, status, and onboarding origin.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    Pageable pageable = new Pageable(); // Pageable | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantSummary result = apiInstance.listPartnerMerchants(pageable, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#listPartnerMerchants");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **pageable** | [**Pageable**](.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantSummary**](MerchantSummary.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Merchants retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Partner not found |  -  |

<a id="partnerOnboardMerchant"></a>
# **partnerOnboardMerchant**
> PartnerOnboardingResult partnerOnboardMerchant(merchantOnboardingRequest, acceptLanguage)

Onboard a new merchant

Creates and onboards a new merchant under the authenticated partner. The merchant will receive an activation email to complete registration.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    MerchantOnboardingRequest merchantOnboardingRequest = new MerchantOnboardingRequest(); // MerchantOnboardingRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PartnerOnboardingResult result = apiInstance.partnerOnboardMerchant(merchantOnboardingRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#partnerOnboardMerchant");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantOnboardingRequest** | [**MerchantOnboardingRequest**](MerchantOnboardingRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PartnerOnboardingResult**](PartnerOnboardingResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Merchant onboarded successfully |  -  |
| **400** | Invalid request body |  -  |
| **401** | Unauthorized |  -  |
| **404** | Partner not found |  -  |

<a id="searchPartnerMerchants"></a>
# **searchPartnerMerchants**
> PageResponseListMerchantSummary searchPartnerMerchants(searchMerchantsRequest, acceptLanguage)

Search partner merchants

Advanced search over the authenticated partner&#39;s merchants with full-text query, filters, sorting, and pagination. Partner scope is enforced server-side.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    SearchMerchantsRequest searchMerchantsRequest = new SearchMerchantsRequest(); // SearchMerchantsRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      PageResponseListMerchantSummary result = apiInstance.searchPartnerMerchants(searchMerchantsRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#searchPartnerMerchants");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **searchMerchantsRequest** | [**SearchMerchantsRequest**](SearchMerchantsRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**PageResponseListMerchantSummary**](PageResponseListMerchantSummary.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="suspendPartnerMerchant"></a>
# **suspendPartnerMerchant**
> MerchantDetail suspendPartnerMerchant(merchantId, acceptLanguage)

Suspend merchant

Sets the merchant&#39;s account status to SUSPENDED. Partner-scoped (404 if not owned).

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    UUID merchantId = UUID.randomUUID(); // UUID | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantDetail result = apiInstance.suspendPartnerMerchant(merchantId, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#suspendPartnerMerchant");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **UUID**|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantDetail**](MerchantDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |

<a id="updatePartnerMerchant"></a>
# **updatePartnerMerchant**
> MerchantDetail updatePartnerMerchant(merchantId, merchantUpdateRequest, acceptLanguage)

Update merchant profile

Updates editable profile fields of one of the partner&#39;s merchants. Null fields are left unchanged. Account email and status are not editable here.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.PartnerMerchantsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    PartnerMerchantsApi apiInstance = new PartnerMerchantsApi(defaultClient);
    UUID merchantId = UUID.randomUUID(); // UUID | 
    MerchantUpdateRequest merchantUpdateRequest = new MerchantUpdateRequest(); // MerchantUpdateRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      MerchantDetail result = apiInstance.updatePartnerMerchant(merchantId, merchantUpdateRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PartnerMerchantsApi#updatePartnerMerchant");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **merchantId** | **UUID**|  | |
| **merchantUpdateRequest** | [**MerchantUpdateRequest**](MerchantUpdateRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**MerchantDetail**](MerchantDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |


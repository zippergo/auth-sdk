# PartnerMerchantsApi

All URIs are relative to *http://localhost:8080*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getPartnerMerchantByEmail**](PartnerMerchantsApi.md#getPartnerMerchantByEmail) | **GET** /auth/partners/merchants/by-email | Get merchant by email |
| [**getPartnerMerchantStatus**](PartnerMerchantsApi.md#getPartnerMerchantStatus) | **GET** /auth/partners/merchants/{merchantId}/status | Get merchant onboarding status |
| [**listPartnerMerchants**](PartnerMerchantsApi.md#listPartnerMerchants) | **GET** /auth/partners/merchants | List partner merchants |
| [**partnerOnboardMerchant**](PartnerMerchantsApi.md#partnerOnboardMerchant) | **POST** /auth/partners/merchants | Onboard a new merchant |


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


# MerchantApiKeysApi

All URIs are relative to *http://localhost:8080*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createApiKey**](MerchantApiKeysApi.md#createApiKey) | **POST** /auth/merchants/api-keys | Create a new API key |
| [**listApiKeys**](MerchantApiKeysApi.md#listApiKeys) | **GET** /auth/merchants/api-keys | List all API keys |
| [**revokeApiKey**](MerchantApiKeysApi.md#revokeApiKey) | **DELETE** /auth/merchants/api-keys/{id} | Revoke an API key |


<a id="createApiKey"></a>
# **createApiKey**
> ApiKeyCreatedResponse createApiKey(createApiKeyRequest, acceptLanguage)

Create a new API key

Generates a new API key pair (apiKey and apiSecret) for the authenticated merchant. The apiSecret is only returned once at creation time and cannot be retrieved later.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.MerchantApiKeysApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MerchantApiKeysApi apiInstance = new MerchantApiKeysApi(defaultClient);
    CreateApiKeyRequest createApiKeyRequest = new CreateApiKeyRequest(); // CreateApiKeyRequest | 
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      ApiKeyCreatedResponse result = apiInstance.createApiKey(createApiKeyRequest, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MerchantApiKeysApi#createApiKey");
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
| **createApiKeyRequest** | [**CreateApiKeyRequest**](CreateApiKeyRequest.md)|  | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**ApiKeyCreatedResponse**](ApiKeyCreatedResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | API key created successfully |  -  |
| **400** | Invalid request body |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden – requires MERCHANT role with PASSWORD auth |  -  |

<a id="listApiKeys"></a>
# **listApiKeys**
> ApiKeySummary listApiKeys(acceptLanguage)

List all API keys

Returns a summary of all API keys belonging to the authenticated merchant, including status and usage metadata.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.MerchantApiKeysApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MerchantApiKeysApi apiInstance = new MerchantApiKeysApi(defaultClient);
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      ApiKeySummary result = apiInstance.listApiKeys(acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling MerchantApiKeysApi#listApiKeys");
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

[**ApiKeySummary**](ApiKeySummary.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | API keys retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden – requires MERCHANT role with PASSWORD auth |  -  |

<a id="revokeApiKey"></a>
# **revokeApiKey**
> revokeApiKey(id, acceptLanguage)

Revoke an API key

Permanently revokes the specified API key. The key will no longer be usable for authentication.

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.MerchantApiKeysApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP bearer authorization: bearerAuth
    HttpBearerAuth bearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("bearerAuth");
    bearerAuth.setBearerToken("BEARER TOKEN");

    MerchantApiKeysApi apiInstance = new MerchantApiKeysApi(defaultClient);
    UUID id = UUID.randomUUID(); // UUID | API key identifier
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      apiInstance.revokeApiKey(id, acceptLanguage);
    } catch (ApiException e) {
      System.err.println("Exception when calling MerchantApiKeysApi#revokeApiKey");
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
| **id** | **UUID**| API key identifier | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

null (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | API key revoked successfully |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden – requires MERCHANT role with PASSWORD auth |  -  |
| **404** | API key not found |  -  |


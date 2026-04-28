# OAuth2Api

All URIs are relative to *http://localhost:8080*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**token**](OAuth2Api.md#token) | **POST** /oauth/token | Exchange client credentials for an access token |


<a id="token"></a>
# **token**
> TokenResponse token(authorization, grantType, acceptLanguage)

Exchange client credentials for an access token

Issues a JWT access token in exchange for valid API client credentials using the client_credentials grant type. Credentials must be provided via HTTP Basic Authentication (Base64-encoded apiKey:apiSecret).

### Example
```java
// Import classes:
import com.zipper.auth.sdk.ApiClient;
import com.zipper.auth.sdk.ApiException;
import com.zipper.auth.sdk.Configuration;
import com.zipper.auth.sdk.auth.*;
import com.zipper.auth.sdk.models.*;
import com.zipper.auth.sdk.api.OAuth2Api;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8080");
    
    // Configure HTTP basic authorization: basicAuth
    HttpBasicAuth basicAuth = (HttpBasicAuth) defaultClient.getAuthentication("basicAuth");
    basicAuth.setUsername("YOUR USERNAME");
    basicAuth.setPassword("YOUR PASSWORD");

    OAuth2Api apiInstance = new OAuth2Api(defaultClient);
    String authorization = "authorization_example"; // String | Basic Authentication header (Base64-encoded apiKey:apiSecret)
    String grantType = "grantType_example"; // String | OAuth2 grant type (must be 'client_credentials')
    String acceptLanguage = "en"; // String | Language preference for response content. Supported: en, he
    try {
      TokenResponse result = apiInstance.token(authorization, grantType, acceptLanguage);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling OAuth2Api#token");
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
| **authorization** | **String**| Basic Authentication header (Base64-encoded apiKey:apiSecret) | |
| **grantType** | **String**| OAuth2 grant type (must be &#39;client_credentials&#39;) | |
| **acceptLanguage** | **String**| Language preference for response content. Supported: en, he | [optional] [default to en] [enum: en, he] |

### Return type

[**TokenResponse**](TokenResponse.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Access token issued successfully |  -  |
| **400** | Unsupported grant type |  -  |
| **401** | Invalid client credentials |  -  |
| **500** | Internal server error |  -  |


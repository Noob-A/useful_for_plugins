# DefaultApi

All URIs are relative to *http://localhost:8000*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getGet**](DefaultApi.md#getGet) | **GET** /get | Retrieve a list of products


<a name="getGet"></a>
# **getGet**
> List&lt;Product&gt; getGet(sort, param, type, minPrice, maxPrice, authorId, version)

Retrieve a list of products

Returns a list of products that match the specified criteria.

### Example
```java
// Import classes:
import org.openapitools.client.ApiClient;
import org.openapitools.client.ApiException;
import org.openapitools.client.Configuration;
import org.openapitools.client.models.*;
import org.openapitools.client.api.DefaultApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:8000");

    DefaultApi apiInstance = new DefaultApi(defaultClient);
    String sort = "sort_example"; // String | Sort order for the results. Must be either \"ascending\" or \"descending\".
    String param = "param_example"; // String | The parameter to sort the results by. Must be a valid column name in the Product table.
    String type = "type_example"; // String | The type of product to retrieve. Must be one of \"plugins\", \"themes\", or \"other\".
    Integer minPrice = 56; // Integer | The minimum price of the products to retrieve.
    Integer maxPrice = 56; // Integer | The maximum price of the products to retrieve.
    Integer authorId = 56; // Integer | The ID of the author of the products to retrieve.
    String version = "version_example"; // String | The version of the products to retrieve.
    try {
      List<Product> result = apiInstance.getGet(sort, param, type, minPrice, maxPrice, authorId, version);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling DefaultApi#getGet");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sort** | **String**| Sort order for the results. Must be either \&quot;ascending\&quot; or \&quot;descending\&quot;. | [optional]
 **param** | **String**| The parameter to sort the results by. Must be a valid column name in the Product table. | [optional]
 **type** | **String**| The type of product to retrieve. Must be one of \&quot;plugins\&quot;, \&quot;themes\&quot;, or \&quot;other\&quot;. | [optional]
 **minPrice** | **Integer**| The minimum price of the products to retrieve. | [optional]
 **maxPrice** | **Integer**| The maximum price of the products to retrieve. | [optional]
 **authorId** | **Integer**| The ID of the author of the products to retrieve. | [optional]
 **version** | **String**| The version of the products to retrieve. | [optional]

### Return type

[**List&lt;Product&gt;**](Product.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A list of products that match the specified criteria. |  -  |


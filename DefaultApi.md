# openapi_client.DefaultApi

All URIs are relative to *http://localhost:8000*

Method | HTTP request | Description
------------- | ------------- | -------------
[**products_delete_delete**](DefaultApi.md#products_delete_delete) | **DELETE** /products/delete | Delete a product by ID or author ID
[**products_get_get**](DefaultApi.md#products_get_get) | **GET** /products/get | Retrieve a list of products
[**products_modify_put**](DefaultApi.md#products_modify_put) | **PUT** /products/modify | Modify a product


# **products_delete_delete**
> products_delete_delete()

Delete a product by ID or author ID

Deletes a product from the database by its ID or author ID.

### Example

```python
import time
import openapi_client
from openapi_client.api import default_api
from pprint import pprint
# Defining the host is optional and defaults to http://localhost:8000
# See configuration.py for a list of all supported configuration parameters.
configuration = openapi_client.Configuration(
    host = "http://localhost:8000"
)


# Enter a context with an instance of the API client
with openapi_client.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)
    product_id = 1 # int | The ID of the product to delete. (optional)
    author_id = 1 # int | The ID of the author of the product to delete. (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Delete a product by ID or author ID
        api_instance.products_delete_delete(product_id=product_id, author_id=author_id)
    except openapi_client.ApiException as e:
        print("Exception when calling DefaultApi->products_delete_delete: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **product_id** | **int**| The ID of the product to delete. | [optional]
 **author_id** | **int**| The ID of the author of the product to delete. | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | The product was successfully deleted. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **products_get_get**
> [Product] products_get_get()

Retrieve a list of products

Returns a list of products that match the specified criteria.

### Example

```python
import time
import openapi_client
from openapi_client.api import default_api
from openapi_client.model.product import Product
from pprint import pprint
# Defining the host is optional and defaults to http://localhost:8000
# See configuration.py for a list of all supported configuration parameters.
configuration = openapi_client.Configuration(
    host = "http://localhost:8000"
)


# Enter a context with an instance of the API client
with openapi_client.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)
    sort = "sort_example" # str | Sort order for the results. Must be either \"ascending\" or \"descending\". (optional)
    param = "param_example" # str | The parameter to sort the results by. Must be a valid column name in the Product table. (optional)
    type = "type_example" # str | The type of product to retrieve. Must be one of \"plugins\", \"themes\", or \"other\". (optional)
    min_price = 1 # int | The minimum price of the products to retrieve. (optional)
    max_price = 1 # int | The maximum price of the products to retrieve. (optional)
    author_id = 1 # int | The ID of the author of the products to retrieve. (optional)
    version = "version_example" # str | The version of the products to retrieve. (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve a list of products
        api_response = api_instance.products_get_get(sort=sort, param=param, type=type, min_price=min_price, max_price=max_price, author_id=author_id, version=version)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling DefaultApi->products_get_get: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **sort** | **str**| Sort order for the results. Must be either \&quot;ascending\&quot; or \&quot;descending\&quot;. | [optional]
 **param** | **str**| The parameter to sort the results by. Must be a valid column name in the Product table. | [optional]
 **type** | **str**| The type of product to retrieve. Must be one of \&quot;plugins\&quot;, \&quot;themes\&quot;, or \&quot;other\&quot;. | [optional]
 **min_price** | **int**| The minimum price of the products to retrieve. | [optional]
 **max_price** | **int**| The maximum price of the products to retrieve. | [optional]
 **author_id** | **int**| The ID of the author of the products to retrieve. | [optional]
 **version** | **str**| The version of the products to retrieve. | [optional]

### Return type

[**[Product]**](Product.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A list of products that match the specified criteria. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **products_modify_put**
> Product products_modify_put(product_id, product_update)

Modify a product

Modify a product with the specified ID.

### Example

```python
import time
import openapi_client
from openapi_client.api import default_api
from openapi_client.model.product import Product
from openapi_client.model.product_update import ProductUpdate
from pprint import pprint
# Defining the host is optional and defaults to http://localhost:8000
# See configuration.py for a list of all supported configuration parameters.
configuration = openapi_client.Configuration(
    host = "http://localhost:8000"
)


# Enter a context with an instance of the API client
with openapi_client.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)
    product_id = 1 # int | The ID of the product to modify.
    product_update = ProductUpdate(
        name="name_example",
        description="description_example",
        price=0,
        product_type="plugin",
        version="version_example",
        author_id=1,
    ) # ProductUpdate | 

    # example passing only required values which don't have defaults set
    try:
        # Modify a product
        api_response = api_instance.products_modify_put(product_id, product_update)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling DefaultApi->products_modify_put: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **product_id** | **int**| The ID of the product to modify. |
 **product_update** | [**ProductUpdate**](ProductUpdate.md)|  |

### Return type

[**Product**](Product.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | The modified product. |  -  |
**400** | Invalid request payload or parameters. |  -  |
**404** | Product not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


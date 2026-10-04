# LLMPulse::StoreIntegrationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**accept_catalog_prompt_suggestions**](StoreIntegrationsApi.md#accept_catalog_prompt_suggestions) | **POST** /catalog_prompt_suggestions/accept | Accept catalog prompt suggestions |
| [**create_catalog_prompt_suggestions**](StoreIntegrationsApi.md#create_catalog_prompt_suggestions) | **POST** /catalog_prompt_suggestions | Suggest buyer prompts from catalog products |
| [**get_store_connection**](StoreIntegrationsApi.md#get_store_connection) | **GET** /store_connection | Match a store to a project |
| [**list_ai_orders**](StoreIntegrationsApi.md#list_ai_orders) | **GET** /ai_orders | Read AI-referred store orders |
| [**list_catalog_prompt_suggestions**](StoreIntegrationsApi.md#list_catalog_prompt_suggestions) | **GET** /catalog_prompt_suggestions | List catalog prompt suggestions |
| [**reject_catalog_prompt_suggestions**](StoreIntegrationsApi.md#reject_catalog_prompt_suggestions) | **POST** /catalog_prompt_suggestions/reject | Reject catalog prompt suggestions |
| [**replace_ai_orders**](StoreIntegrationsApi.md#replace_ai_orders) | **PUT** /ai_orders | Replace AI-referred store orders for a window |


## accept_catalog_prompt_suggestions

> <CatalogPromptSuggestionsAcceptResponse> accept_catalog_prompt_suggestions(catalog_prompt_suggestion_ids_request)

Accept catalog prompt suggestions

Starts tracking pending suggestions: each one becomes a prompt, tagged with a collection named after its product. Suggestions that are no longer pending come back in skipped. All accepted suggestions must share one country and language. When the new prompts would exceed the plan, the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a `read_write` scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::StoreIntegrationsApi.new
catalog_prompt_suggestion_ids_request = LLMPulse::CatalogPromptSuggestionIdsRequest.new({project_id: 37, ids: [37]}) # CatalogPromptSuggestionIdsRequest | 

begin
  # Accept catalog prompt suggestions
  result = api_instance.accept_catalog_prompt_suggestions(catalog_prompt_suggestion_ids_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->accept_catalog_prompt_suggestions: #{e}"
end
```

#### Using the accept_catalog_prompt_suggestions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CatalogPromptSuggestionsAcceptResponse>, Integer, Hash)> accept_catalog_prompt_suggestions_with_http_info(catalog_prompt_suggestion_ids_request)

```ruby
begin
  # Accept catalog prompt suggestions
  data, status_code, headers = api_instance.accept_catalog_prompt_suggestions_with_http_info(catalog_prompt_suggestion_ids_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CatalogPromptSuggestionsAcceptResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->accept_catalog_prompt_suggestions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **catalog_prompt_suggestion_ids_request** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md) |  |  |

### Return type

[**CatalogPromptSuggestionsAcceptResponse**](CatalogPromptSuggestionsAcceptResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_catalog_prompt_suggestions

> <CatalogPromptSuggestionsCreateResponse> create_catalog_prompt_suggestions(catalog_prompt_suggestions_create_request)

Suggest buyer prompts from catalog products

Writes buyer prompts for up to 20 catalog products and saves them as pending suggestions in the project's Suggested prompts queue, with the product recorded on each. Generation draws on the hourly prompt-suggestion allowance the app also uses (ERR_QUOTA_EXCEEDED once it is used up); a failed generation returns ERR_GENERATION_FAILED (502) and can be retried. Requires a `read_write` scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::StoreIntegrationsApi.new
catalog_prompt_suggestions_create_request = LLMPulse::CatalogPromptSuggestionsCreateRequest.new({project_id: 37, platform: 'shopify', products: [LLMPulse::CatalogProduct.new({external_id: 'external_id_example', title: 'title_example'})]}) # CatalogPromptSuggestionsCreateRequest | 

begin
  # Suggest buyer prompts from catalog products
  result = api_instance.create_catalog_prompt_suggestions(catalog_prompt_suggestions_create_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->create_catalog_prompt_suggestions: #{e}"
end
```

#### Using the create_catalog_prompt_suggestions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CatalogPromptSuggestionsCreateResponse>, Integer, Hash)> create_catalog_prompt_suggestions_with_http_info(catalog_prompt_suggestions_create_request)

```ruby
begin
  # Suggest buyer prompts from catalog products
  data, status_code, headers = api_instance.create_catalog_prompt_suggestions_with_http_info(catalog_prompt_suggestions_create_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CatalogPromptSuggestionsCreateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->create_catalog_prompt_suggestions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **catalog_prompt_suggestions_create_request** | [**CatalogPromptSuggestionsCreateRequest**](CatalogPromptSuggestionsCreateRequest.md) |  |  |

### Return type

[**CatalogPromptSuggestionsCreateResponse**](CatalogPromptSuggestionsCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_store_connection

> <StoreConnectionResponse> get_store_connection(platform, domain)

Match a store to a project

Tells a store app whether the API key's account can use it and which project the store belongs to: the live project whose domain equals the store domain, else one whose domain is a parent or a subdomain of it, else null. candidates lists every live project of the account so the app can offer a picker. Takes no project_id. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::StoreIntegrationsApi.new
platform = 'shopify' # String | Store platform
domain = 'domain_example' # String | Store domain, with or without scheme, e.g. acme-store.com

begin
  # Match a store to a project
  result = api_instance.get_store_connection(platform, domain)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->get_store_connection: #{e}"
end
```

#### Using the get_store_connection_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<StoreConnectionResponse>, Integer, Hash)> get_store_connection_with_http_info(platform, domain)

```ruby
begin
  # Match a store to a project
  data, status_code, headers = api_instance.get_store_connection_with_http_info(platform, domain)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <StoreConnectionResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->get_store_connection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform** | **String** | Store platform |  |
| **domain** | **String** | Store domain, with or without scheme, e.g. acme-store.com |  |

### Return type

[**StoreConnectionResponse**](StoreConnectionResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_ai_orders

> <AiOrdersResponse> list_ai_orders(project_id, opts)

Read AI-referred store orders

Reads back the AI-referred orders a store app pushed for a project: totals, one row per AI assistant and a daily series of the days with orders. Revenue values are decimal strings in currency. Team members need read access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::StoreIntegrationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  platform: 'shopify', # String | Store platform
  from: Date.parse('2013-10-20'), # Date | First day (YYYY-MM-DD). Defaults to 89 days before to
  to: Date.parse('2013-10-20') # Date | Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days
}

begin
  # Read AI-referred store orders
  result = api_instance.list_ai_orders(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->list_ai_orders: #{e}"
end
```

#### Using the list_ai_orders_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AiOrdersResponse>, Integer, Hash)> list_ai_orders_with_http_info(project_id, opts)

```ruby
begin
  # Read AI-referred store orders
  data, status_code, headers = api_instance.list_ai_orders_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AiOrdersResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->list_ai_orders_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **platform** | **String** | Store platform | [optional][default to &#39;shopify&#39;] |
| **from** | **Date** | First day (YYYY-MM-DD). Defaults to 89 days before to | [optional] |
| **to** | **Date** | Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days | [optional] |

### Return type

[**AiOrdersResponse**](AiOrdersResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_catalog_prompt_suggestions

> <CatalogPromptSuggestionsResponse> list_catalog_prompt_suggestions(project_id, opts)

List catalog prompt suggestions

Lists the buyer prompts suggested from a store catalog, oldest first, with their status and the product each one came from. Team members need read access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::StoreIntegrationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  status: 'pending', # String | Only suggestions in this status
  product_external_id: 'product_external_id_example', # String | Only suggestions for this store product id
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List catalog prompt suggestions
  result = api_instance.list_catalog_prompt_suggestions(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->list_catalog_prompt_suggestions: #{e}"
end
```

#### Using the list_catalog_prompt_suggestions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CatalogPromptSuggestionsResponse>, Integer, Hash)> list_catalog_prompt_suggestions_with_http_info(project_id, opts)

```ruby
begin
  # List catalog prompt suggestions
  data, status_code, headers = api_instance.list_catalog_prompt_suggestions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CatalogPromptSuggestionsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->list_catalog_prompt_suggestions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **status** | **String** | Only suggestions in this status | [optional] |
| **product_external_id** | **String** | Only suggestions for this store product id | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 50] |

### Return type

[**CatalogPromptSuggestionsResponse**](CatalogPromptSuggestionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## reject_catalog_prompt_suggestions

> <CatalogPromptSuggestionsRejectResponse> reject_catalog_prompt_suggestions(catalog_prompt_suggestion_ids_request)

Reject catalog prompt suggestions

Marks pending suggestions as rejected; suggestions that are no longer pending stay as they are. Requires a `read_write` scope API key and, for team members, update access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::StoreIntegrationsApi.new
catalog_prompt_suggestion_ids_request = LLMPulse::CatalogPromptSuggestionIdsRequest.new({project_id: 37, ids: [37]}) # CatalogPromptSuggestionIdsRequest | 

begin
  # Reject catalog prompt suggestions
  result = api_instance.reject_catalog_prompt_suggestions(catalog_prompt_suggestion_ids_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->reject_catalog_prompt_suggestions: #{e}"
end
```

#### Using the reject_catalog_prompt_suggestions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CatalogPromptSuggestionsRejectResponse>, Integer, Hash)> reject_catalog_prompt_suggestions_with_http_info(catalog_prompt_suggestion_ids_request)

```ruby
begin
  # Reject catalog prompt suggestions
  data, status_code, headers = api_instance.reject_catalog_prompt_suggestions_with_http_info(catalog_prompt_suggestion_ids_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CatalogPromptSuggestionsRejectResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->reject_catalog_prompt_suggestions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **catalog_prompt_suggestion_ids_request** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md) |  |  |

### Return type

[**CatalogPromptSuggestionsRejectResponse**](CatalogPromptSuggestionsRejectResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## replace_ai_orders

> <AiOrdersUpdateResponse> replace_ai_orders(ai_orders_update_request)

Replace AI-referred store orders for a window

Replaces the daily AI-referred orders and revenue of the from..to window. Send the raw referring host or utm_source of each order's first visit as referrer: LLM Pulse classifies it and ignores anything that is not an AI assistant. Entries for the same day and assistant are summed. Every stored row of that project and platform inside the window is replaced, so pushing the same window again converges instead of counting twice. Rows are kept per project and platform, not per store, so one store reports per project. Requires a `read_write` scope API key and, for team members, update access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::StoreIntegrationsApi.new
ai_orders_update_request = LLMPulse::AiOrdersUpdateRequest.new({project_id: 37, platform: 'shopify', currency: 'currency_example', from: Date.today, to: Date.today, days: [LLMPulse::AiOrdersUpdateRequestDaysInner.new({day: Date.today, referrer: 'referrer_example', orders: 37, revenue: 'revenue_example'})]}) # AiOrdersUpdateRequest | 

begin
  # Replace AI-referred store orders for a window
  result = api_instance.replace_ai_orders(ai_orders_update_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->replace_ai_orders: #{e}"
end
```

#### Using the replace_ai_orders_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AiOrdersUpdateResponse>, Integer, Hash)> replace_ai_orders_with_http_info(ai_orders_update_request)

```ruby
begin
  # Replace AI-referred store orders for a window
  data, status_code, headers = api_instance.replace_ai_orders_with_http_info(ai_orders_update_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AiOrdersUpdateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling StoreIntegrationsApi->replace_ai_orders_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ai_orders_update_request** | [**AiOrdersUpdateRequest**](AiOrdersUpdateRequest.md) |  |  |

### Return type

[**AiOrdersUpdateResponse**](AiOrdersUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


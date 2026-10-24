# LLMPulse::RecommendationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_recommendation**](RecommendationsApi.md#get_recommendation) | **GET** /recommendations/{id} | Get recommendation run with items |
| [**launch_recommendations**](RecommendationsApi.md#launch_recommendations) | **POST** /recommendations | Launch a recommendations generation |
| [**list_recommendations**](RecommendationsApi.md#list_recommendations) | **GET** /recommendations | List recommendation runs |
| [**update_recommendation_item**](RecommendationsApi.md#update_recommendation_item) | **PATCH** /recommendations/{id}/items/{item_id} | Complete, archive or restore a recommendation item |


## get_recommendation

> get_recommendation(project_id, id, opts)

Get recommendation run with items

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::RecommendationsApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 
opts = {
  item_status: 'active', # String | 
  resolve_source_refs: true # Boolean | 
}

begin
  # Get recommendation run with items
  api_instance.get_recommendation(project_id, id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling RecommendationsApi->get_recommendation: #{e}"
end
```

#### Using the get_recommendation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_recommendation_with_http_info(project_id, id, opts)

```ruby
begin
  # Get recommendation run with items
  data, status_code, headers = api_instance.get_recommendation_with_http_info(project_id, id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling RecommendationsApi->get_recommendation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **Integer** |  |  |
| **item_status** | **String** |  | [optional] |
| **resolve_source_refs** | **Boolean** |  | [optional][default to true] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## launch_recommendations

> launch_recommendations(launch_recommendations_request)

Launch a recommendations generation

Launches a full-scope recommendations generation (async job, 1-3 minutes; poll GET /recommendations/{id} until status is completed). Consumes the project weekly recommendation-item budget: returns ERR_LIMIT_REACHED when it is exhausted or when a generation of the same type is already pending/processing. sentiment_reputation requires the Scale plan or above. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::RecommendationsApi.new
launch_recommendations_request = LLMPulse::LaunchRecommendationsRequest.new({project_id: 37}) # LaunchRecommendationsRequest | 

begin
  # Launch a recommendations generation
  api_instance.launch_recommendations(launch_recommendations_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling RecommendationsApi->launch_recommendations: #{e}"
end
```

#### Using the launch_recommendations_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> launch_recommendations_with_http_info(launch_recommendations_request)

```ruby
begin
  # Launch a recommendations generation
  data, status_code, headers = api_instance.launch_recommendations_with_http_info(launch_recommendations_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling RecommendationsApi->launch_recommendations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **launch_recommendations_request** | [**LaunchRecommendationsRequest**](LaunchRecommendationsRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_recommendations

> <RecommendationsResponse> list_recommendations(project_id, opts)

List recommendation runs

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::RecommendationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  recommendation_type: 'ai_visibility', # String | 
  status: 'pending', # String | 
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List recommendation runs
  result = api_instance.list_recommendations(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling RecommendationsApi->list_recommendations: #{e}"
end
```

#### Using the list_recommendations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RecommendationsResponse>, Integer, Hash)> list_recommendations_with_http_info(project_id, opts)

```ruby
begin
  # List recommendation runs
  data, status_code, headers = api_instance.list_recommendations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RecommendationsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling RecommendationsApi->list_recommendations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **recommendation_type** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

[**RecommendationsResponse**](RecommendationsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_recommendation_item

> <RecommendationItemUpdateResponse> update_recommendation_item(id, item_id, update_recommendation_item_request)

Complete, archive or restore a recommendation item

Moves one item of a recommendation run between `active`, `completed` and `archived`, exactly like the complete, archive and restore buttons on the Recommendations page, and stamps `status_changed_at`. When archiving, an optional `reason` teaches later runs: `not_relevant` and `too_complex` steer the next recommendations away from similar ones, and on a PR & Citation Building item that targets a domain (`metadata.domain`), `competitor` or `not_relevant` stops that site from being suggested again. The reason is stored in `metadata.archive_reason` and dropped when the item leaves `archived`. A reason with another status, an unknown one, or `competitor` on an item without a domain returns `ERR_INVALID_PARAM`. Returns the item in the shape `GET /recommendations/{id}` lists items. Requires a `read_write` scope API key and, for team members, create permission on Recommendations (the permission the page uses for these buttons).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::RecommendationsApi.new
id = 56 # Integer | Recommendation run id
item_id = 56 # Integer | Item id, from the items of GET /recommendations/{id}
update_recommendation_item_request = LLMPulse::UpdateRecommendationItemRequest.new({project_id: 37, status: 'active'}) # UpdateRecommendationItemRequest | 

begin
  # Complete, archive or restore a recommendation item
  result = api_instance.update_recommendation_item(id, item_id, update_recommendation_item_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling RecommendationsApi->update_recommendation_item: #{e}"
end
```

#### Using the update_recommendation_item_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<RecommendationItemUpdateResponse>, Integer, Hash)> update_recommendation_item_with_http_info(id, item_id, update_recommendation_item_request)

```ruby
begin
  # Complete, archive or restore a recommendation item
  data, status_code, headers = api_instance.update_recommendation_item_with_http_info(id, item_id, update_recommendation_item_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <RecommendationItemUpdateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling RecommendationsApi->update_recommendation_item_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | Recommendation run id |  |
| **item_id** | **Integer** | Item id, from the items of GET /recommendations/{id} |  |
| **update_recommendation_item_request** | [**UpdateRecommendationItemRequest**](UpdateRecommendationItemRequest.md) |  |  |

### Return type

[**RecommendationItemUpdateResponse**](RecommendationItemUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


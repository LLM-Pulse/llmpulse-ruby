# LLMPulse::RecommendationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_recommendation**](RecommendationsApi.md#get_recommendation) | **GET** /recommendations/{id} | Get recommendation run with items |
| [**launch_recommendations**](RecommendationsApi.md#launch_recommendations) | **POST** /recommendations | Launch a recommendations generation |
| [**list_recommendations**](RecommendationsApi.md#list_recommendations) | **GET** /recommendations | List recommendation runs |


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

> list_recommendations(project_id, opts)

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
  api_instance.list_recommendations(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling RecommendationsApi->list_recommendations: #{e}"
end
```

#### Using the list_recommendations_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_recommendations_with_http_info(project_id, opts)

```ruby
begin
  # List recommendation runs
  data, status_code, headers = api_instance.list_recommendations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
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

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


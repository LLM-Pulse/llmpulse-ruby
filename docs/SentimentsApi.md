# LLMPulse::SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**list_sentiment_records**](SentimentsApi.md#list_sentiment_records) | **GET** /sentiments | List sentiment records |


## list_sentiment_records

> list_sentiment_records(project_id, opts)

List sentiment records

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SentimentsApi.new
project_id = 56 # Integer | Project ID
opts = {
  competitor_id: 56, # Integer | 
  brand_only: true, # Boolean | 
  analysis: 'very_positive', # String | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List sentiment records
  api_instance.list_sentiment_records(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SentimentsApi->list_sentiment_records: #{e}"
end
```

#### Using the list_sentiment_records_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_sentiment_records_with_http_info(project_id, opts)

```ruby
begin
  # List sentiment records
  data, status_code, headers = api_instance.list_sentiment_records_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SentimentsApi->list_sentiment_records_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **competitor_id** | **Integer** |  | [optional] |
| **brand_only** | **Boolean** |  | [optional] |
| **analysis** | **String** |  | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


# LLMPulse::SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**list_sentiment_categories**](SentimentsApi.md#list_sentiment_categories) | **GET** /dimensions/sentiments | List sentiment categories |
| [**list_sentiment_records**](SentimentsApi.md#list_sentiment_records) | **GET** /sentiments | List sentiment records |


## list_sentiment_categories

> list_sentiment_categories(project_id, opts)

List sentiment categories

Sentiment metric keys + labels + colors. For records, use /sentiments.

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
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List sentiment categories
  api_instance.list_sentiment_categories(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SentimentsApi->list_sentiment_categories: #{e}"
end
```

#### Using the list_sentiment_categories_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_sentiment_categories_with_http_info(project_id, opts)

```ruby
begin
  # List sentiment categories
  data, status_code, headers = api_instance.list_sentiment_categories_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SentimentsApi->list_sentiment_categories_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


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
  analysis: 'analysis_example', # String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
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
| **analysis** | **String** | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


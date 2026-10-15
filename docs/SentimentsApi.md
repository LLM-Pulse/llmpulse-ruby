# LLMPulse::SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_sentiment_tags**](SentimentsApi.md#get_sentiment_tags) | **GET** /reports/sentiment/tags | Sentiment by tag (Growth plan or above) |
| [**get_sentiment_topics**](SentimentsApi.md#get_sentiment_topics) | **GET** /reports/sentiment/topics | Sentiment by topic (Growth plan or above) |
| [**list_sentiment_categories**](SentimentsApi.md#list_sentiment_categories) | **GET** /dimensions/sentiments | List sentiment categories (Growth plan or above) |
| [**list_sentiment_records**](SentimentsApi.md#list_sentiment_records) | **GET** /sentiments | List sentiment records (Growth plan or above) |


## get_sentiment_tags

> <SentimentTagsResponse> get_sentiment_tags(project_id, opts)

Sentiment by tag (Growth plan or above)

One row per tag of the project with at least one analyzed mention, with the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score. A mention counts once for every tag its prompt carries, as on the Sentiment page. Same filters as GET /reports/sentiment/topics. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

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
  range: 56, # Integer | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  analysis: 'analysis_example', # String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
  topic: 'topic_example', # String | Only sentiments tagged with this topic (case-insensitive)
  query: 'query_example', # String | Only sentiments whose answer or prompt text contains this text
  brand: 'brand_example', # String | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM).
  sort: 'mentions', # String | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name.
  sort_dir: 'desc', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Sentiment by tag (Growth plan or above)
  result = api_instance.get_sentiment_tags(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SentimentsApi->get_sentiment_tags: #{e}"
end
```

#### Using the get_sentiment_tags_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SentimentTagsResponse>, Integer, Hash)> get_sentiment_tags_with_http_info(project_id, opts)

```ruby
begin
  # Sentiment by tag (Growth plan or above)
  data, status_code, headers = api_instance.get_sentiment_tags_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SentimentTagsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SentimentsApi->get_sentiment_tags_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **analysis** | **String** | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **topic** | **String** | Only sentiments tagged with this topic (case-insensitive) | [optional] |
| **query** | **String** | Only sentiments whose answer or prompt text contains this text | [optional] |
| **brand** | **String** | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional] |
| **sort** | **String** | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional][default to &#39;mentions&#39;] |
| **sort_dir** | **String** |  | [optional][default to &#39;desc&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**SentimentTagsResponse**](SentimentTagsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_sentiment_topics

> <SentimentTopicsResponse> get_sentiment_topics(project_id, opts)

Sentiment by topic (Growth plan or above)

One row per topic AI answers associate with the brand (topics are matched case-insensitively), with its analyzed mentions, the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score ((positive - negative) / mentions x 100). The same rows and filters as the Topics tab of the Sentiment page: the window defaults to the last 28 days, `brand` empty counts your own brand, `all` every brand and a competitor id that competitor. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

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
  range: 56, # Integer | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  analysis: 'analysis_example', # String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
  topic: 'topic_example', # String | Only sentiments tagged with this topic (case-insensitive)
  query: 'query_example', # String | Only sentiments whose answer or prompt text contains this text
  brand: 'brand_example', # String | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM).
  sort: 'mentions', # String | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name.
  sort_dir: 'desc', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Sentiment by topic (Growth plan or above)
  result = api_instance.get_sentiment_topics(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SentimentsApi->get_sentiment_topics: #{e}"
end
```

#### Using the get_sentiment_topics_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SentimentTopicsResponse>, Integer, Hash)> get_sentiment_topics_with_http_info(project_id, opts)

```ruby
begin
  # Sentiment by topic (Growth plan or above)
  data, status_code, headers = api_instance.get_sentiment_topics_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SentimentTopicsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SentimentsApi->get_sentiment_topics_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **analysis** | **String** | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **topic** | **String** | Only sentiments tagged with this topic (case-insensitive) | [optional] |
| **query** | **String** | Only sentiments whose answer or prompt text contains this text | [optional] |
| **brand** | **String** | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional] |
| **sort** | **String** | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional][default to &#39;mentions&#39;] |
| **sort_dir** | **String** |  | [optional][default to &#39;desc&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**SentimentTopicsResponse**](SentimentTopicsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_sentiment_categories

> list_sentiment_categories(project_id, opts)

List sentiment categories (Growth plan or above)

Sentiment metric keys + labels + colors. For records, use /sentiments. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

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
  # List sentiment categories (Growth plan or above)
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
  # List sentiment categories (Growth plan or above)
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
- **Accept**: application/json


## list_sentiment_records

> <SentimentsResponse> list_sentiment_records(project_id, opts)

List sentiment records (Growth plan or above)

Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

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
  model: 'chatgpt', # String | Filter by one AI model. Here an unknown value, or a model the API key's user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List sentiment records (Growth plan or above)
  result = api_instance.list_sentiment_records(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SentimentsApi->list_sentiment_records: #{e}"
end
```

#### Using the list_sentiment_records_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SentimentsResponse>, Integer, Hash)> list_sentiment_records_with_http_info(project_id, opts)

```ruby
begin
  # List sentiment records (Growth plan or above)
  data, status_code, headers = api_instance.list_sentiment_records_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SentimentsResponse>
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
| **model** | **String** | Filter by one AI model. Here an unknown value, or a model the API key&#39;s user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

[**SentimentsResponse**](SentimentsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


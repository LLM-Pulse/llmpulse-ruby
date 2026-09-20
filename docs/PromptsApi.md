# LLMPulse::PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_prompts**](PromptsApi.md#create_prompts) | **POST** /prompts | Bulk-create prompts |
| [**delete_prompt**](PromptsApi.md#delete_prompt) | **DELETE** /prompts/{id} | Delete a prompt |
| [**list_prompt_executions**](PromptsApi.md#list_prompt_executions) | **GET** /dimensions/prompt_executions | List prompt executions |
| [**list_prompts**](PromptsApi.md#list_prompts) | **GET** /dimensions/prompts | List prompts |
| [**list_query_fan_outs**](PromptsApi.md#list_query_fan_outs) | **GET** /dimensions/query_fan_outs | List query fan-out |


## create_prompts

> <PromptsCreateResponse> create_prompts(prompts_create_request)

Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::PromptsApi.new
prompts_create_request = LLMPulse::PromptsCreateRequest.new({project_id: 37, prompts: ['prompts_example'], country_code: 'country_code_example', language_code: 'language_code_example'}) # PromptsCreateRequest | 

begin
  # Bulk-create prompts
  result = api_instance.create_prompts(prompts_create_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->create_prompts: #{e}"
end
```

#### Using the create_prompts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PromptsCreateResponse>, Integer, Hash)> create_prompts_with_http_info(prompts_create_request)

```ruby
begin
  # Bulk-create prompts
  data, status_code, headers = api_instance.create_prompts_with_http_info(prompts_create_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PromptsCreateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->create_prompts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompts_create_request** | [**PromptsCreateRequest**](PromptsCreateRequest.md) |  |  |

### Return type

[**PromptsCreateResponse**](PromptsCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_prompt

> delete_prompt(project_id, id)

Delete a prompt

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::PromptsApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 

begin
  # Delete a prompt
  api_instance.delete_prompt(project_id, id)
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->delete_prompt: #{e}"
end
```

#### Using the delete_prompt_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_prompt_with_http_info(project_id, id)

```ruby
begin
  # Delete a prompt
  data, status_code, headers = api_instance.delete_prompt_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->delete_prompt_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **Integer** |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_prompt_executions

> list_prompt_executions(project_id, opts)

List prompt executions

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::PromptsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  mention_filter: 'mentions_you', # String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
  citation_filter: 'cites_you', # String | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List prompt executions
  api_instance.list_prompt_executions(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_prompt_executions: #{e}"
end
```

#### Using the list_prompt_executions_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_prompt_executions_with_http_info(project_id, opts)

```ruby
begin
  # List prompt executions
  data, status_code, headers = api_instance.list_prompt_executions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_prompt_executions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **mention_filter** | **String** | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] |
| **citation_filter** | **String** | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_prompts

> list_prompts(project_id, opts)

List prompts

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::PromptsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List prompts
  api_instance.list_prompts(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_prompts: #{e}"
end
```

#### Using the list_prompts_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_prompts_with_http_info(project_id, opts)

```ruby
begin
  # List prompts
  data, status_code, headers = api_instance.list_prompts_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_prompts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_query_fan_outs

> list_query_fan_outs(project_id, opts)

List query fan-out

The sub-queries a model actually issued when answering your tracked prompts. view=query (default) returns one row per distinct sub-query with count and share of all occurrences; view=prompt returns one row per prompt with how many distinct sub-queries it produced. Fan-out is reported mainly by ChatGPT, so an empty result usually means the models in scope do not expose it. The API returns the aggregation only: for a period-over-period delta, call it twice with explicit from/to.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::PromptsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  view: 'query', # String | Row shape: one per distinct sub-query, or one per prompt
  order: 'count', # String | Sort field; the allowed set depends on view
  direction: 'asc', # String | 
  query: 'query_example', # String | Case-insensitive substring filter on the sub-query text
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List query fan-out
  api_instance.list_query_fan_outs(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_query_fan_outs: #{e}"
end
```

#### Using the list_query_fan_outs_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_query_fan_outs_with_http_info(project_id, opts)

```ruby
begin
  # List query fan-out
  data, status_code, headers = api_instance.list_query_fan_outs_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_query_fan_outs_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **view** | **String** | Row shape: one per distinct sub-query, or one per prompt | [optional][default to &#39;query&#39;] |
| **order** | **String** | Sort field; the allowed set depends on view | [optional] |
| **direction** | **String** |  | [optional][default to &#39;desc&#39;] |
| **query** | **String** | Case-insensitive substring filter on the sub-query text | [optional] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


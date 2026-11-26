# LLMPulse::MentionsCitationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**list_all_citations**](MentionsCitationsApi.md#list_all_citations) | **GET** /dimensions/all_citations | List all citations (brand + competitor) |
| [**list_all_mentions**](MentionsCitationsApi.md#list_all_mentions) | **GET** /dimensions/all_mentions | List all mentions (brand + competitor) |
| [**list_citations**](MentionsCitationsApi.md#list_citations) | **GET** /dimensions/citations | List brand citations |
| [**list_competitor_citations**](MentionsCitationsApi.md#list_competitor_citations) | **GET** /dimensions/competitor_citations | List competitor citations |
| [**list_competitor_mentions**](MentionsCitationsApi.md#list_competitor_mentions) | **GET** /dimensions/competitor_mentions | List competitor mentions |
| [**list_mentions**](MentionsCitationsApi.md#list_mentions) | **GET** /dimensions/mentions | List brand mentions |


## list_all_citations

> <AllCitationsResponse> list_all_citations(project_id, opts)

List all citations (brand + competitor)

Unified citations stream with an `actor_type` field on each record. Includes visible citations and background source references; background references use position 0, meaning no visible rank.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MentionsCitationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM)
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56 # Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
}

begin
  # List all citations (brand + competitor)
  result = api_instance.list_all_citations(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_all_citations: #{e}"
end
```

#### Using the list_all_citations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AllCitationsResponse>, Integer, Hash)> list_all_citations_with_http_info(project_id, opts)

```ruby
begin
  # List all citations (brand + competitor)
  data, status_code, headers = api_instance.list_all_citations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AllCitationsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_all_citations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **competitors** | **String** | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **from** | **Time** | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**AllCitationsResponse**](AllCitationsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_all_mentions

> <AllMentionsResponse> list_all_mentions(project_id, opts)

List all mentions (brand + competitor)

Unified mentions stream. Each record has an `actor_type` field (`project` or `competitor`) so the same payload covers both.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MentionsCitationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM)
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56 # Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
}

begin
  # List all mentions (brand + competitor)
  result = api_instance.list_all_mentions(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_all_mentions: #{e}"
end
```

#### Using the list_all_mentions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AllMentionsResponse>, Integer, Hash)> list_all_mentions_with_http_info(project_id, opts)

```ruby
begin
  # List all mentions (brand + competitor)
  data, status_code, headers = api_instance.list_all_mentions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AllMentionsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_all_mentions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **competitors** | **String** | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **from** | **Time** | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**AllMentionsResponse**](AllMentionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_citations

> <CitationsResponse> list_citations(project_id, opts)

List brand citations

Includes visible citations and background source references. Background references use position 0, meaning no visible rank.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MentionsCitationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56 # Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
}

begin
  # List brand citations
  result = api_instance.list_citations(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_citations: #{e}"
end
```

#### Using the list_citations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CitationsResponse>, Integer, Hash)> list_citations_with_http_info(project_id, opts)

```ruby
begin
  # List brand citations
  data, status_code, headers = api_instance.list_citations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CitationsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_citations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **from** | **Time** | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**CitationsResponse**](CitationsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_competitor_citations

> <CompetitorCitationsResponse> list_competitor_citations(project_id, opts)

List competitor citations

Includes visible citations and background source references. Background references use position 0, meaning no visible rank.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MentionsCitationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM)
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56 # Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
}

begin
  # List competitor citations
  result = api_instance.list_competitor_citations(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_competitor_citations: #{e}"
end
```

#### Using the list_competitor_citations_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CompetitorCitationsResponse>, Integer, Hash)> list_competitor_citations_with_http_info(project_id, opts)

```ruby
begin
  # List competitor citations
  data, status_code, headers = api_instance.list_competitor_citations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CompetitorCitationsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_competitor_citations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **competitors** | **String** | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **from** | **Time** | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**CompetitorCitationsResponse**](CompetitorCitationsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_competitor_mentions

> <CompetitorMentionsResponse> list_competitor_mentions(project_id, opts)

List competitor mentions

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MentionsCitationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM)
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56 # Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
}

begin
  # List competitor mentions
  result = api_instance.list_competitor_mentions(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_competitor_mentions: #{e}"
end
```

#### Using the list_competitor_mentions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CompetitorMentionsResponse>, Integer, Hash)> list_competitor_mentions_with_http_info(project_id, opts)

```ruby
begin
  # List competitor mentions
  data, status_code, headers = api_instance.list_competitor_mentions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CompetitorMentionsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_competitor_mentions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **competitors** | **String** | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **from** | **Time** | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**CompetitorMentionsResponse**](CompetitorMentionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_mentions

> <MentionsResponse> list_mentions(project_id, opts)

List brand mentions

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::MentionsCitationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56 # Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
}

begin
  # List brand mentions
  result = api_instance.list_mentions(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_mentions: #{e}"
end
```

#### Using the list_mentions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<MentionsResponse>, Integer, Hash)> list_mentions_with_http_info(project_id, opts)

```ruby
begin
  # List brand mentions
  data, status_code, headers = api_instance.list_mentions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <MentionsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling MentionsCitationsApi->list_mentions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **from** | **Time** | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**MentionsResponse**](MentionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


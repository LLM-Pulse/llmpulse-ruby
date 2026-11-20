# LLMPulse::SourcesCitationIntelligenceApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**add_url_list_entries**](SourcesCitationIntelligenceApi.md#add_url_list_entries) | **POST** /url_lists/{id}/entries | Add entries to a URL list |
| [**create_url_list**](SourcesCitationIntelligenceApi.md#create_url_list) | **POST** /url_lists | Create a URL list |
| [**delete_url_list**](SourcesCitationIntelligenceApi.md#delete_url_list) | **DELETE** /url_lists/{id} | Delete a URL list |
| [**get_cited_url_content**](SourcesCitationIntelligenceApi.md#get_cited_url_content) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**get_cited_url_detail**](SourcesCitationIntelligenceApi.md#get_cited_url_detail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**get_mentions_by_citing_domain**](SourcesCitationIntelligenceApi.md#get_mentions_by_citing_domain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**get_url_list**](SourcesCitationIntelligenceApi.md#get_url_list) | **GET** /url_lists/{id} | Get a URL list report |
| [**list_citation_groups**](SourcesCitationIntelligenceApi.md#list_citation_groups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**list_cited_url_occurrences**](SourcesCitationIntelligenceApi.md#list_cited_url_occurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |
| [**list_sources**](SourcesCitationIntelligenceApi.md#list_sources) | **GET** /dimensions/sources | List source URLs |
| [**list_url_lists**](SourcesCitationIntelligenceApi.md#list_url_lists) | **GET** /url_lists | List URL lists |
| [**remove_url_list_entries**](SourcesCitationIntelligenceApi.md#remove_url_list_entries) | **POST** /url_lists/{id}/entries/remove | Remove entries from a URL list |
| [**update_url_list**](SourcesCitationIntelligenceApi.md#update_url_list) | **PATCH** /url_lists/{id} | Update a URL list |


## add_url_list_entries

> <UrlListEntriesAddResponse> add_url_list_entries(id, url_list_entries_add_request)

Add entries to a URL list

Adds entries, as POST /url_lists reads them. A rule the list already holds keeps its place and takes only the added_on, cost and channel this request sends for it. Values that do not parse come back in invalid_entries. Requires a `read_write` scope API key and the Growth plan.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
id = 56 # Integer | 
url_list_entries_add_request = LLMPulse::UrlListEntriesAddRequest.new({project_id: 37, entries: [LLMPulse::UrlListEntryInput.new({value: 'value_example'})]}) # UrlListEntriesAddRequest | 

begin
  # Add entries to a URL list
  result = api_instance.add_url_list_entries(id, url_list_entries_add_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->add_url_list_entries: #{e}"
end
```

#### Using the add_url_list_entries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UrlListEntriesAddResponse>, Integer, Hash)> add_url_list_entries_with_http_info(id, url_list_entries_add_request)

```ruby
begin
  # Add entries to a URL list
  data, status_code, headers = api_instance.add_url_list_entries_with_http_info(id, url_list_entries_add_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UrlListEntriesAddResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->add_url_list_entries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **url_list_entries_add_request** | [**UrlListEntriesAddRequest**](UrlListEntriesAddRequest.md) |  |  |

### Return type

[**UrlListEntriesAddResponse**](UrlListEntriesAddResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_url_list

> <UrlListCreateResponse> create_url_list(url_list_create_request)

Create a URL list

Creates a URL list. Each entry is a string or an object with value, match_type, added_on (YYYY-MM-DD, default today), cost (in the list currency) and channel. Without a match_type, \"acme.com/blog/*\" is a prefix, a value with a path or query an exact URL and a bare host a domain. A list holds at most 1000 entries and a project at most 100 lists; the name is unique per project, case-insensitive. Refusals answer ERR_INVALID_PARAM with a reason token in error.meta.reason. Requires a `read_write` scope API key and the Growth plan.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
url_list_create_request = LLMPulse::UrlListCreateRequest.new({project_id: 37, name: 'name_example'}) # UrlListCreateRequest | 

begin
  # Create a URL list
  result = api_instance.create_url_list(url_list_create_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->create_url_list: #{e}"
end
```

#### Using the create_url_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UrlListCreateResponse>, Integer, Hash)> create_url_list_with_http_info(url_list_create_request)

```ruby
begin
  # Create a URL list
  data, status_code, headers = api_instance.create_url_list_with_http_info(url_list_create_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UrlListCreateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->create_url_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **url_list_create_request** | [**UrlListCreateRequest**](UrlListCreateRequest.md) |  |  |

### Return type

[**UrlListCreateResponse**](UrlListCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_url_list

> <UrlListDeleteResponse> delete_url_list(project_id, id)

Delete a URL list

Deletes a URL list and its entries. Citation data is not affected. Requires a `read_write` scope API key and the Growth plan.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 

begin
  # Delete a URL list
  result = api_instance.delete_url_list(project_id, id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->delete_url_list: #{e}"
end
```

#### Using the delete_url_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UrlListDeleteResponse>, Integer, Hash)> delete_url_list_with_http_info(project_id, id)

```ruby
begin
  # Delete a URL list
  data, status_code, headers = api_instance.delete_url_list_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UrlListDeleteResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->delete_url_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **Integer** |  |  |

### Return type

[**UrlListDeleteResponse**](UrlListDeleteResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_cited_url_content

> get_cited_url_content(project_id, url_sha256)

Cited URL cached content

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
url_sha256 = 'url_sha256_example' # String | 64-character hex SHA-256 of the cited URL

begin
  # Cited URL cached content
  api_instance.get_cited_url_content(project_id, url_sha256)
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->get_cited_url_content: #{e}"
end
```

#### Using the get_cited_url_content_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_cited_url_content_with_http_info(project_id, url_sha256)

```ruby
begin
  # Cited URL cached content
  data, status_code, headers = api_instance.get_cited_url_content_with_http_info(project_id, url_sha256)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->get_cited_url_content_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **url_sha256** | **String** | 64-character hex SHA-256 of the cited URL |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_cited_url_detail

> get_cited_url_detail(project_id, url_sha256, opts)

Cited URL detail

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is. The filters narrow stats and citation_series alike. citation_series (with include_series=true) holds the answers citing the URL under the same filters: granularity (day, week or month, from the account tracking cadence, with weeks when a daily account spans more than 60 days, starting on Monday), total (equal to total_responses), by_model (answers per AI model, largest first, which can include enabled models outside the seven the model filter accepts) and data, one { date, value } point per period that holds a filtered answer, so a zero means answers ran and none cited it. Periods date each answer by the day it was created in Europe/Madrid time, the date from and to filter.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
url_sha256 = 'url_sha256_example' # String | 64-character hex SHA-256 of the cited URL
opts = {
  model: 'chatgpt', # String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  source_type: 'owned', # String | 
  sentiment: 'negative', # String | Keeps the citations of answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED.
  content_gap: 'mentioned', # String | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match.
  include_series: true # Boolean | Adds citation_series. Without it the response is unchanged.
}

begin
  # Cited URL detail
  api_instance.get_cited_url_detail(project_id, url_sha256, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->get_cited_url_detail: #{e}"
end
```

#### Using the get_cited_url_detail_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_cited_url_detail_with_http_info(project_id, url_sha256, opts)

```ruby
begin
  # Cited URL detail
  data, status_code, headers = api_instance.get_cited_url_detail_with_http_info(project_id, url_sha256, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->get_cited_url_detail_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **url_sha256** | **String** | 64-character hex SHA-256 of the cited URL |  |
| **model** | **String** | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **source_type** | **String** |  | [optional] |
| **sentiment** | **String** | Keeps the citations of answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED. | [optional] |
| **content_gap** | **String** | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match. | [optional] |
| **include_series** | **Boolean** | Adds citation_series. Without it the response is unchanged. | [optional][default to false] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_mentions_by_citing_domain

> get_mentions_by_citing_domain(project_id, domains, opts)

Mention share by citing domain

For the responses where each given source domain is cited, returns the share of those responses that mention the brand vs each competitor (brand + competitors sum to 100% per domain). Pass multiple domains to get the whole matrix in one call.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
domains = ['inner_example'] # Array<String> | Source domains to analyze: one domain or a comma-separated list, e.g. domains=gmac.com,educaweb.com. The bracket form domains[]=gmac.com&domains[]=educaweb.com is also accepted.
opts = {
  model: 'chatgpt', # String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00') # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
}

begin
  # Mention share by citing domain
  api_instance.get_mentions_by_citing_domain(project_id, domains, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->get_mentions_by_citing_domain: #{e}"
end
```

#### Using the get_mentions_by_citing_domain_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_mentions_by_citing_domain_with_http_info(project_id, domains, opts)

```ruby
begin
  # Mention share by citing domain
  data, status_code, headers = api_instance.get_mentions_by_citing_domain_with_http_info(project_id, domains, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->get_mentions_by_citing_domain_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **domains** | [**Array&lt;String&gt;**](String.md) | Source domains to analyze: one domain or a comma-separated list, e.g. domains&#x3D;gmac.com,educaweb.com. The bracket form domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com is also accepted. |  |
| **model** | **String** | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_url_list

> <UrlListDetailResponse> get_url_list(id, project_id, opts)

Get a URL list report

The list, its summary (entries_count, cited_entries, citations, answers in the window, citation_rate, avg_citation_position, median_days_to_first_citation, total_cost, cost_per_cited_entry) and a page of its entries. An entry's status is cited (an answer cited it in the window), lost (cited before the window, not in it) or not_cited. first_cited_at reads the filtered answers up to the window's end. days_to_first_citation is null before the first citation or when the page was cited before it was added. brand_mentioned is set for exact URLs once their page was read, else null. Without from/to or range the window is all time. Requires the Growth plan.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
id = 56 # Integer | 
project_id = 56 # Integer | Project ID
opts = {
  status: 'cited', # String | Only entries with this status.
  order: 'value', # String | 
  direction: 'asc', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  range: 56 # Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
}

begin
  # Get a URL list report
  result = api_instance.get_url_list(id, project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->get_url_list: #{e}"
end
```

#### Using the get_url_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UrlListDetailResponse>, Integer, Hash)> get_url_list_with_http_info(id, project_id, opts)

```ruby
begin
  # Get a URL list report
  data, status_code, headers = api_instance.get_url_list_with_http_info(id, project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UrlListDetailResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->get_url_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **project_id** | **Integer** | Project ID |  |
| **status** | **String** | Only entries with this status. | [optional] |
| **order** | **String** |  | [optional][default to &#39;citations&#39;] |
| **direction** | **String** |  | [optional][default to &#39;desc&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**UrlListDetailResponse**](UrlListDetailResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_citation_groups

> list_citation_groups(project_id, opts)

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position=0. Owned and competitor source matching honor the project's exact-subdomain setting. Filter vocabulary aligns with `source_type` returned by the API. Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is. Pass key to read one group; brand_kind filters by the brand focus of the prompts, like the source page. citation_series (with include_series=true) holds the answers citing the URL, domain or host under the same filters: granularity (day, week or month, from the account tracking cadence, with weeks when a daily account spans more than 60 days, starting on Monday), total (equal to total_responses), by_model (answers per AI model, largest first, which can include enabled models outside the seven the model filter accepts) and data, one { date, value } point per period that holds a filtered answer, so a zero means answers ran and none cited it. Periods date each answer by the day it was created in Europe/Madrid time, the date from and to filter.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
opts = {
  view: 'url', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  order: 'group_key', # String | 
  direction: 'asc', # String | 
  model: 'chatgpt', # String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  key: 'key_example', # String | Return only this group of the chosen view: a domain (view=domain), a host (view=host) or a cited URL exactly as listed (view=url). Domains and hosts match case-insensitively, without www. A view=url key is one raw URL, so its variants (a tracking parameter, a trailing slash) stay separate rows; GET /citation_intelligence/urls/{url_sha256} merges them, as the app does. No match returns an empty list (total 0), not an error.
  include_series: true, # Boolean | Requires key, else 422 ERR_INVALID_PARAM. Adds citation_series to the group's row.
  query: 'query_example', # String | 
  source_type: 'owned', # String | 
  sentiment: 'negative', # String | Keeps the citations of answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED.
  content_gap: 'mentioned' # String | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match.
}

begin
  # Grouped citation intelligence
  api_instance.list_citation_groups(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->list_citation_groups: #{e}"
end
```

#### Using the list_citation_groups_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_citation_groups_with_http_info(project_id, opts)

```ruby
begin
  # Grouped citation intelligence
  data, status_code, headers = api_instance.list_citation_groups_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->list_citation_groups_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **view** | **String** |  | [optional][default to &#39;url&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **order** | **String** |  | [optional] |
| **direction** | **String** |  | [optional] |
| **model** | **String** | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **key** | **String** | Return only this group of the chosen view: a domain (view&#x3D;domain), a host (view&#x3D;host) or a cited URL exactly as listed (view&#x3D;url). Domains and hosts match case-insensitively, without www. A view&#x3D;url key is one raw URL, so its variants (a tracking parameter, a trailing slash) stay separate rows; GET /citation_intelligence/urls/{url_sha256} merges them, as the app does. No match returns an empty list (total 0), not an error. | [optional] |
| **include_series** | **Boolean** | Requires key, else 422 ERR_INVALID_PARAM. Adds citation_series to the group&#39;s row. | [optional][default to false] |
| **query** | **String** |  | [optional] |
| **source_type** | **String** |  | [optional] |
| **sentiment** | **String** | Keeps the citations of answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED. | [optional] |
| **content_gap** | **String** | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_cited_url_occurrences

> list_cited_url_occurrences(project_id, url_sha256, opts)

Cited URL occurrences

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
url_sha256 = 'url_sha256_example' # String | 64-character hex SHA-256 of the cited URL
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  sentiment: 'negative' # String | Keeps the occurrences in answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED.
}

begin
  # Cited URL occurrences
  api_instance.list_cited_url_occurrences(project_id, url_sha256, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->list_cited_url_occurrences: #{e}"
end
```

#### Using the list_cited_url_occurrences_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_cited_url_occurrences_with_http_info(project_id, url_sha256, opts)

```ruby
begin
  # Cited URL occurrences
  data, status_code, headers = api_instance.list_cited_url_occurrences_with_http_info(project_id, url_sha256, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->list_cited_url_occurrences_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **url_sha256** | **String** | 64-character hex SHA-256 of the cited URL |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **sentiment** | **String** | Keeps the occurrences in answers with a negative brand sentiment. Needs the Growth plan or above: below it the filter answers 403 ERR_PLAN_REQUIRED. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_sources

> list_sources(project_id, opts)

List source URLs

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
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
  source_type: 'owned', # String | Filter by source ownership. Owned and competitor matching honor the project's exact-subdomain setting. Any other value, including a differently cased one, returns ERR_INVALID_PARAM.
  mention_filter: 'mentions_you', # String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space; on answers, finished answers only). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM)
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  range: 56 # Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
}

begin
  # List source URLs
  api_instance.list_sources(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->list_sources: #{e}"
end
```

#### Using the list_sources_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_sources_with_http_info(project_id, opts)

```ruby
begin
  # List source URLs
  data, status_code, headers = api_instance.list_sources_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->list_sources_with_http_info: #{e}"
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
| **source_type** | **String** | Filter by source ownership. Owned and competitor matching honor the project&#39;s exact-subdomain setting. Any other value, including a differently cased one, returns ERR_INVALID_PARAM. | [optional] |
| **mention_filter** | **String** | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space; on answers, finished answers only). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] |
| **competitors** | **String** | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_url_lists

> <UrlListsResponse> list_url_lists(project_id, opts)

List URL lists

A URL list is a named set of rules, each an exact URL (matched over http and https, with or without www), a URL prefix (every page under host/path) or a domain (the site and its subdomains). Its numbers count the AI answers to the prompts tracked in the project: cited_entries is the entries an answer cited in the window and citations the answers citing any entry, each once. Without from/to or range the window is all time. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
opts = {
  model: 'chatgpt', # String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  range: 56 # Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
}

begin
  # List URL lists
  result = api_instance.list_url_lists(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->list_url_lists: #{e}"
end
```

#### Using the list_url_lists_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UrlListsResponse>, Integer, Hash)> list_url_lists_with_http_info(project_id, opts)

```ruby
begin
  # List URL lists
  data, status_code, headers = api_instance.list_url_lists_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UrlListsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->list_url_lists_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **model** | **String** | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **range** | **Integer** | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**UrlListsResponse**](UrlListsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## remove_url_list_entries

> <UrlListEntriesRemoveResponse> remove_url_list_entries(id, url_list_entries_remove_request)

Remove entries from a URL list

Removes entries by id (from GET /url_lists/{id}) or by value as written (\"https://acme.com/a\", \"acme.com/blog/*\", \"acme.com\"). Sending neither answers ERR_INVALID_PARAM. Requires a `read_write` scope API key and the Growth plan.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
id = 56 # Integer | 
url_list_entries_remove_request = LLMPulse::UrlListEntriesRemoveRequest.new({project_id: 37}) # UrlListEntriesRemoveRequest | 

begin
  # Remove entries from a URL list
  result = api_instance.remove_url_list_entries(id, url_list_entries_remove_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->remove_url_list_entries: #{e}"
end
```

#### Using the remove_url_list_entries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UrlListEntriesRemoveResponse>, Integer, Hash)> remove_url_list_entries_with_http_info(id, url_list_entries_remove_request)

```ruby
begin
  # Remove entries from a URL list
  data, status_code, headers = api_instance.remove_url_list_entries_with_http_info(id, url_list_entries_remove_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UrlListEntriesRemoveResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->remove_url_list_entries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **url_list_entries_remove_request** | [**UrlListEntriesRemoveRequest**](UrlListEntriesRemoveRequest.md) |  |  |

### Return type

[**UrlListEntriesRemoveResponse**](UrlListEntriesRemoveResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_url_list

> <UrlListUpdateResponse> update_url_list(id, url_list_update_request)

Update a URL list

Changes the name, description or currency of a URL list. Entries are added with POST /url_lists/{id}/entries and removed with POST /url_lists/{id}/entries/remove. Requires a `read_write` scope API key and the Growth plan.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SourcesCitationIntelligenceApi.new
id = 56 # Integer | 
url_list_update_request = LLMPulse::UrlListUpdateRequest.new({project_id: 37}) # UrlListUpdateRequest | 

begin
  # Update a URL list
  result = api_instance.update_url_list(id, url_list_update_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->update_url_list: #{e}"
end
```

#### Using the update_url_list_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UrlListUpdateResponse>, Integer, Hash)> update_url_list_with_http_info(id, url_list_update_request)

```ruby
begin
  # Update a URL list
  data, status_code, headers = api_instance.update_url_list_with_http_info(id, url_list_update_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UrlListUpdateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->update_url_list_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **url_list_update_request** | [**UrlListUpdateRequest**](UrlListUpdateRequest.md) |  |  |

### Return type

[**UrlListUpdateResponse**](UrlListUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


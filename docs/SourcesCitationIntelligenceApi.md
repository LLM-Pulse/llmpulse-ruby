# LLMPulse::SourcesCitationIntelligenceApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_cited_url_content**](SourcesCitationIntelligenceApi.md#get_cited_url_content) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**get_cited_url_detail**](SourcesCitationIntelligenceApi.md#get_cited_url_detail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**get_mentions_by_citing_domain**](SourcesCitationIntelligenceApi.md#get_mentions_by_citing_domain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**list_citation_groups**](SourcesCitationIntelligenceApi.md#list_citation_groups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**list_cited_url_occurrences**](SourcesCitationIntelligenceApi.md#list_cited_url_occurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |
| [**list_sources**](SourcesCitationIntelligenceApi.md#list_sources) | **GET** /dimensions/sources | List source URLs |


## get_cited_url_content

> get_cited_url_content(project_id, url_sha256)

Cited URL cached content

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null; content_gap_status is content_unavailable (or missing_page_cache). Mention arrays stay empty until usable content has completed analysis. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; mention counts are null when no URL has completed analysis.

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

> get_cited_url_detail(project_id, url_sha256)

Cited URL detail

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null; content_gap_status is content_unavailable (or missing_page_cache). Mention arrays stay empty until usable content has completed analysis. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; mention counts are null when no URL has completed analysis.

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
  # Cited URL detail
  api_instance.get_cited_url_detail(project_id, url_sha256)
rescue LLMPulse::ApiError => e
  puts "Error when calling SourcesCitationIntelligenceApi->get_cited_url_detail: #{e}"
end
```

#### Using the get_cited_url_detail_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_cited_url_detail_with_http_info(project_id, url_sha256)

```ruby
begin
  # Cited URL detail
  data, status_code, headers = api_instance.get_cited_url_detail_with_http_info(project_id, url_sha256)
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
domains = ['inner_example'] # Array<String> | Source domains to analyze, e.g. domains[]=gmac.com&domains[]=educaweb.com
opts = {
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
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
| **domains** | [**Array&lt;String&gt;**](String.md) | Source domains to analyze, e.g. domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com |  |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
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


## list_citation_groups

> list_citation_groups(project_id, opts)

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position=0. Owned and competitor source matching honor the project's exact-subdomain setting. Filter vocabulary aligns with `source_type` returned by the API. Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null; content_gap_status is content_unavailable (or missing_page_cache). Mention arrays stay empty until usable content has completed analysis. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; mention counts are null when no URL has completed analysis.

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
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  query: 'query_example', # String | 
  source_type: 'owned', # String | 
  sentiment: 'negative', # String | 
  content_gap: 'mentioned' # String | 
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
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **query** | **String** |  | [optional] |
| **source_type** | **String** |  | [optional] |
| **sentiment** | **String** |  | [optional] |
| **content_gap** | **String** |  | [optional] |

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
  per_page: 56 # Integer | 
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
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: nil, # GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  source_type: 'owned', # String | Filter by source ownership. Owned and competitor matching honor the project's exact-subdomain setting.
  mention_filter: 'mentions_you', # String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
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
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | [**GetTimeseriesCollectionIdParameter**](.md) | One collection/tag ID or a comma-separated list of IDs | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **source_type** | **String** | Filter by source ownership. Owned and competitor matching honor the project&#39;s exact-subdomain setting. | [optional] |
| **mention_filter** | **String** | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


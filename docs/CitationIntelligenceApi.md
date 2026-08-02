# LLMPulse::CitationIntelligenceApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_cited_url_content**](CitationIntelligenceApi.md#get_cited_url_content) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**get_cited_url_detail**](CitationIntelligenceApi.md#get_cited_url_detail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**get_mentions_by_citing_domain**](CitationIntelligenceApi.md#get_mentions_by_citing_domain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**list_citation_groups**](CitationIntelligenceApi.md#list_citation_groups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**list_cited_url_occurrences**](CitationIntelligenceApi.md#list_cited_url_occurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |


## get_cited_url_content

> get_cited_url_content(project_id, url_sha256)

Cited URL cached content

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
url_sha256 = 'url_sha256_example' # String | 64-character hex SHA-256 of the cited URL

begin
  # Cited URL cached content
  api_instance.get_cited_url_content(project_id, url_sha256)
rescue LLMPulse::ApiError => e
  puts "Error when calling CitationIntelligenceApi->get_cited_url_content: #{e}"
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
  puts "Error when calling CitationIntelligenceApi->get_cited_url_content_with_http_info: #{e}"
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

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
url_sha256 = 'url_sha256_example' # String | 64-character hex SHA-256 of the cited URL

begin
  # Cited URL detail
  api_instance.get_cited_url_detail(project_id, url_sha256)
rescue LLMPulse::ApiError => e
  puts "Error when calling CitationIntelligenceApi->get_cited_url_detail: #{e}"
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
  puts "Error when calling CitationIntelligenceApi->get_cited_url_detail_with_http_info: #{e}"
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

api_instance = LLMPulse::CitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
domains = ['inner_example'] # Array<String> | Source domains to analyze, e.g. domains[]=gmac.com&domains[]=educaweb.com
opts = {
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00') # Time | 
}

begin
  # Mention share by citing domain
  api_instance.get_mentions_by_citing_domain(project_id, domains, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling CitationIntelligenceApi->get_mentions_by_citing_domain: #{e}"
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
  puts "Error when calling CitationIntelligenceApi->get_mentions_by_citing_domain_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **domains** | [**Array&lt;String&gt;**](String.md) | Source domains to analyze, e.g. domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com |  |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |

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

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position=0. Owned and competitor source matching honor the project's exact-subdomain setting. Filter vocabulary aligns with `source_type` returned by the API.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CitationIntelligenceApi.new
project_id = 56 # Integer | Project ID
opts = {
  view: 'url', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  order: 'group_key', # String | 
  direction: 'asc', # String | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  query: 'query_example', # String | 
  source_type: 'owned', # String | 
  sentiment: 'negative', # String | 
  content_gap: 'mentioned' # String | 
}

begin
  # Grouped citation intelligence
  api_instance.list_citation_groups(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling CitationIntelligenceApi->list_citation_groups: #{e}"
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
  puts "Error when calling CitationIntelligenceApi->list_citation_groups_with_http_info: #{e}"
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
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
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

api_instance = LLMPulse::CitationIntelligenceApi.new
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
  puts "Error when calling CitationIntelligenceApi->list_cited_url_occurrences: #{e}"
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
  puts "Error when calling CitationIntelligenceApi->list_cited_url_occurrences_with_http_info: #{e}"
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


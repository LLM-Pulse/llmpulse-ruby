# LLMPulse::DimensionsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_competitor_details**](DimensionsApi.md#get_competitor_details) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**get_project_details**](DimensionsApi.md#get_project_details) | **GET** /dimensions/projects/{id} | Project details |
| [**list_agent_bots**](DimensionsApi.md#list_agent_bots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale+) |
| [**list_all_citations**](DimensionsApi.md#list_all_citations) | **GET** /dimensions/all_citations | List all citations (brand + competitor) |
| [**list_all_mentions**](DimensionsApi.md#list_all_mentions) | **GET** /dimensions/all_mentions | List all mentions (brand + competitor) |
| [**list_citations**](DimensionsApi.md#list_citations) | **GET** /dimensions/citations | List brand citations |
| [**list_collections**](DimensionsApi.md#list_collections) | **GET** /dimensions/collections | List tags/collections |
| [**list_competitor_citations**](DimensionsApi.md#list_competitor_citations) | **GET** /dimensions/competitor_citations | List competitor citations |
| [**list_competitor_mentions**](DimensionsApi.md#list_competitor_mentions) | **GET** /dimensions/competitor_mentions | List competitor mentions |
| [**list_competitors**](DimensionsApi.md#list_competitors) | **GET** /dimensions/competitors | List competitors |
| [**list_locales**](DimensionsApi.md#list_locales) | **GET** /dimensions/locales | List locales with data |
| [**list_mentions**](DimensionsApi.md#list_mentions) | **GET** /dimensions/mentions | List brand mentions |
| [**list_models**](DimensionsApi.md#list_models) | **GET** /dimensions/models | List models with data |
| [**list_projects**](DimensionsApi.md#list_projects) | **GET** /dimensions/projects | List projects |
| [**list_prompt_executions**](DimensionsApi.md#list_prompt_executions) | **GET** /dimensions/prompt_executions | List prompt executions |
| [**list_prompts**](DimensionsApi.md#list_prompts) | **GET** /dimensions/prompts | List prompts |
| [**list_sentiment_categories**](DimensionsApi.md#list_sentiment_categories) | **GET** /dimensions/sentiments | List sentiment categories |
| [**list_sources**](DimensionsApi.md#list_sources) | **GET** /dimensions/sources | List source URLs |
| [**list_tags**](DimensionsApi.md#list_tags) | **GET** /dimensions/tags | List tags (alias for /collections) |


## get_competitor_details

> <CompetitorDetails> get_competitor_details(project_id, id)

Competitor details

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 

begin
  # Competitor details
  result = api_instance.get_competitor_details(project_id, id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->get_competitor_details: #{e}"
end
```

#### Using the get_competitor_details_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CompetitorDetails>, Integer, Hash)> get_competitor_details_with_http_info(project_id, id)

```ruby
begin
  # Competitor details
  data, status_code, headers = api_instance.get_competitor_details_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CompetitorDetails>
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->get_competitor_details_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **Integer** |  |  |

### Return type

[**CompetitorDetails**](CompetitorDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_project_details

> <ProjectDetails> get_project_details(id)

Project details

Detailed info for one project: matching_names, industry, business model, primary products, target audience, brand voice, locale, app store IDs, stats (incl. prompts_by_brand_kind counts) and data_coverage (models, countries and languages with data).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::DimensionsApi.new
id = 56 # Integer | 

begin
  # Project details
  result = api_instance.get_project_details(id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->get_project_details: #{e}"
end
```

#### Using the get_project_details_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ProjectDetails>, Integer, Hash)> get_project_details_with_http_info(id)

```ruby
begin
  # Project details
  data, status_code, headers = api_instance.get_project_details_with_http_info(id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ProjectDetails>
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->get_project_details_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |

### Return type

[**ProjectDetails**](ProjectDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_agent_bots

> <AgentBotsResponse> list_agent_bots(project_id, opts)

AI bot catalog (Scale+)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on all plans.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # AI bot catalog (Scale+)
  result = api_instance.list_agent_bots(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_agent_bots: #{e}"
end
```

#### Using the list_agent_bots_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<AgentBotsResponse>, Integer, Hash)> list_agent_bots_with_http_info(project_id, opts)

```ruby
begin
  # AI bot catalog (Scale+)
  data, status_code, headers = api_instance.list_agent_bots_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <AgentBotsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_agent_bots_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**AgentBotsResponse**](AgentBotsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_all_citations

> list_all_citations(project_id, opts)

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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List all citations (brand + competitor)
  api_instance.list_all_citations(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_all_citations: #{e}"
end
```

#### Using the list_all_citations_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_all_citations_with_http_info(project_id, opts)

```ruby
begin
  # List all citations (brand + competitor)
  data, status_code, headers = api_instance.list_all_citations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_all_citations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_all_mentions

> list_all_mentions(project_id, opts)

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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List all mentions (brand + competitor)
  api_instance.list_all_mentions(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_all_mentions: #{e}"
end
```

#### Using the list_all_mentions_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_all_mentions_with_http_info(project_id, opts)

```ruby
begin
  # List all mentions (brand + competitor)
  data, status_code, headers = api_instance.list_all_mentions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_all_mentions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_citations

> list_citations(project_id, opts)

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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List brand citations
  api_instance.list_citations(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_citations: #{e}"
end
```

#### Using the list_citations_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_citations_with_http_info(project_id, opts)

```ruby
begin
  # List brand citations
  data, status_code, headers = api_instance.list_citations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_citations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_collections

> list_collections(project_id, opts)

List tags/collections

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List tags/collections
  api_instance.list_collections(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_collections: #{e}"
end
```

#### Using the list_collections_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_collections_with_http_info(project_id, opts)

```ruby
begin
  # List tags/collections
  data, status_code, headers = api_instance.list_collections_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_collections_with_http_info: #{e}"
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


## list_competitor_citations

> list_competitor_citations(project_id, opts)

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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List competitor citations
  api_instance.list_competitor_citations(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_competitor_citations: #{e}"
end
```

#### Using the list_competitor_citations_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_competitor_citations_with_http_info(project_id, opts)

```ruby
begin
  # List competitor citations
  data, status_code, headers = api_instance.list_competitor_citations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_competitor_citations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_competitor_mentions

> list_competitor_mentions(project_id, opts)

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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List competitor mentions
  api_instance.list_competitor_mentions(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_competitor_mentions: #{e}"
end
```

#### Using the list_competitor_mentions_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_competitor_mentions_with_http_info(project_id, opts)

```ruby
begin
  # List competitor mentions
  data, status_code, headers = api_instance.list_competitor_mentions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_competitor_mentions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_competitors

> <ListCompetitors200Response> list_competitors(project_id, opts)

List competitors

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  include_project_brand: true, # Boolean | When true, prepends the project brand with actor_type=project and is_own=true
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List competitors
  result = api_instance.list_competitors(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_competitors: #{e}"
end
```

#### Using the list_competitors_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCompetitors200Response>, Integer, Hash)> list_competitors_with_http_info(project_id, opts)

```ruby
begin
  # List competitors
  data, status_code, headers = api_instance.list_competitors_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCompetitors200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_competitors_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **include_project_brand** | **Boolean** | When true, prepends the project brand with actor_type&#x3D;project and is_own&#x3D;true | [optional][default to false] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**ListCompetitors200Response**](ListCompetitors200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_locales

> list_locales(project_id)

List locales with data

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID

begin
  # List locales with data
  api_instance.list_locales(project_id)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_locales: #{e}"
end
```

#### Using the list_locales_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_locales_with_http_info(project_id)

```ruby
begin
  # List locales with data
  data, status_code, headers = api_instance.list_locales_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_locales_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_mentions

> list_mentions(project_id, opts)

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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List brand mentions
  api_instance.list_mentions(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_mentions: #{e}"
end
```

#### Using the list_mentions_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_mentions_with_http_info(project_id, opts)

```ruby
begin
  # List brand mentions
  data, status_code, headers = api_instance.list_mentions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_mentions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_models

> list_models(project_id)

List models with data

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID

begin
  # List models with data
  api_instance.list_models(project_id)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_models: #{e}"
end
```

#### Using the list_models_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_models_with_http_info(project_id)

```ruby
begin
  # List models with data
  data, status_code, headers = api_instance.list_models_with_http_info(project_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_models_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## list_projects

> <ListProjects200Response> list_projects(opts)

List projects

All projects accessible with your API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::DimensionsApi.new
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List projects
  result = api_instance.list_projects(opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_projects: #{e}"
end
```

#### Using the list_projects_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListProjects200Response>, Integer, Hash)> list_projects_with_http_info(opts)

```ruby
begin
  # List projects
  data, status_code, headers = api_instance.list_projects_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListProjects200Response>
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_projects_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**ListProjects200Response**](ListProjects200Response.md)

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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  mention_filter: 'mentions_you', # String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
  citation_filter: 'cites_you', # String | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List prompt executions
  api_instance.list_prompt_executions(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_prompt_executions: #{e}"
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
  puts "Error when calling DimensionsApi->list_prompt_executions_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt_type: 'informational', # String | Filter by prompt type (search intent)
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List prompts
  api_instance.list_prompts(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_prompts: #{e}"
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
  puts "Error when calling DimensionsApi->list_prompts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt_type** | **String** | Filter by prompt type (search intent) | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List sentiment categories
  api_instance.list_sentiment_categories(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_sentiment_categories: #{e}"
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
  puts "Error when calling DimensionsApi->list_sentiment_categories_with_http_info: #{e}"
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

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  model: 'chatgpt', # String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
  collection_id: 56, # Integer | 
  country_code: 'country_code_example', # String | ISO country code (e.g. US, GB, DE)
  language_code: 'language_code_example', # String | ISO language code (e.g. en, es, de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  source_type: 'owned', # String | Filter by source ownership. Owned and competitor matching honor the project's exact-subdomain setting.
  mention_filter: 'mentions_you', # String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List source URLs
  api_instance.list_sources(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_sources: #{e}"
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
  puts "Error when calling DimensionsApi->list_sources_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **model** | **String** | Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] |
| **collection_id** | **Integer** |  | [optional] |
| **country_code** | **String** | ISO country code (e.g. US, GB, DE) | [optional] |
| **language_code** | **String** | ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
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


## list_tags

> list_tags(project_id, opts)

List tags (alias for /collections)

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::DimensionsApi.new
project_id = 56 # Integer | Project ID
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List tags (alias for /collections)
  api_instance.list_tags(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_tags: #{e}"
end
```

#### Using the list_tags_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_tags_with_http_info(project_id, opts)

```ruby
begin
  # List tags (alias for /collections)
  data, status_code, headers = api_instance.list_tags_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling DimensionsApi->list_tags_with_http_info: #{e}"
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


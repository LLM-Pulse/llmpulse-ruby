# LLMPulse::PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**accept_suggested_prompts**](PromptsApi.md#accept_suggested_prompts) | **POST** /suggested_prompts/accept | Accept suggested prompts |
| [**create_prompt_generation**](PromptsApi.md#create_prompt_generation) | **POST** /prompt_generations | Generate prompt suggestions |
| [**create_prompts**](PromptsApi.md#create_prompts) | **POST** /prompts | Bulk-create prompts |
| [**delete_prompt**](PromptsApi.md#delete_prompt) | **DELETE** /prompts/{id} | Delete a prompt |
| [**get_prompt_generation**](PromptsApi.md#get_prompt_generation) | **GET** /prompt_generations/{id} | Get a prompt generation run |
| [**import_prompts**](PromptsApi.md#import_prompts) | **POST** /prompts/import | Import prompts |
| [**list_prompt_executions**](PromptsApi.md#list_prompt_executions) | **GET** /dimensions/prompt_executions | List prompt executions |
| [**list_prompts**](PromptsApi.md#list_prompts) | **GET** /dimensions/prompts | List prompts |
| [**list_query_fan_outs**](PromptsApi.md#list_query_fan_outs) | **GET** /dimensions/query_fan_outs | List query fan-out |
| [**list_suggested_prompts**](PromptsApi.md#list_suggested_prompts) | **GET** /suggested_prompts | List suggested prompts |
| [**reject_suggested_prompts**](PromptsApi.md#reject_suggested_prompts) | **POST** /suggested_prompts/reject | Reject suggested prompts |
| [**update_prompt**](PromptsApi.md#update_prompt) | **PATCH** /prompts/{id} | Edit a prompt&#39;s categorization |


## accept_suggested_prompts

> <SuggestedPromptsAcceptResponse> accept_suggested_prompts(suggested_prompts_accept_request)

Accept suggested prompts

Starts tracking up to 100 pending suggestions: each becomes a prompt in its own country and language, optionally put in one tag (tag_ids or tag_names; create_missing creates a missing name when the team member may create tags). Suggestions that are no longer pending come back in skipped. When the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a `read_write` scope API key and, for team members, create access to Prompts.

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
suggested_prompts_accept_request = LLMPulse::SuggestedPromptsAcceptRequest.new({project_id: 37, ids: [37]}) # SuggestedPromptsAcceptRequest | 

begin
  # Accept suggested prompts
  result = api_instance.accept_suggested_prompts(suggested_prompts_accept_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->accept_suggested_prompts: #{e}"
end
```

#### Using the accept_suggested_prompts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuggestedPromptsAcceptResponse>, Integer, Hash)> accept_suggested_prompts_with_http_info(suggested_prompts_accept_request)

```ruby
begin
  # Accept suggested prompts
  data, status_code, headers = api_instance.accept_suggested_prompts_with_http_info(suggested_prompts_accept_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuggestedPromptsAcceptResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->accept_suggested_prompts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **suggested_prompts_accept_request** | [**SuggestedPromptsAcceptRequest**](SuggestedPromptsAcceptRequest.md) |  |  |

### Return type

[**SuggestedPromptsAcceptResponse**](SuggestedPromptsAcceptResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_prompt_generation

> <PromptGenerationResponse> create_prompt_generation(prompt_generation_request)

Generate prompt suggestions

Starts a suggestion run with one of the generators behind the app's Add prompts wizards and answers 202 with the run. website writes suggestions from the scraped website (80% non-brand, 20% brand; up to 100 per project, then ERR_LIMIT_REACHED), keyword from a keyword or the project profile (optionally around a competitor), topic from a topic, reddit from Reddit discussions of a topic or brand, paa from Google People Also Ask (up to 5 keywords, counted against the account's 24-hour lookup allowance), reputational from brand reputation questions, translate from the project's prompts of another locale, search_console from the connected property's top queries of the last 28 days (Growth plan or above, ERR_PLAN_REQUIRED). The suggestions land in the Suggested prompts queue; poll GET /prompt_generations/{id}, then accept the ones you want with POST /suggested_prompts/accept. Nothing is tracked until accepted. The request is validated before the run starts, and refused with ERR_LIMIT_REACHED when the plan has no prompt slot left, or ERR_QUOTA_EXCEEDED after 60 runs in an hour (the per-user prompt suggestion allowance, shared with project setup). Requires a `read_write` scope API key and, for team members, create access to Prompts.

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
prompt_generation_request = LLMPulse::PromptGenerationRequest.new({project_id: 37, source: 'website'}) # PromptGenerationRequest | 

begin
  # Generate prompt suggestions
  result = api_instance.create_prompt_generation(prompt_generation_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->create_prompt_generation: #{e}"
end
```

#### Using the create_prompt_generation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PromptGenerationResponse>, Integer, Hash)> create_prompt_generation_with_http_info(prompt_generation_request)

```ruby
begin
  # Generate prompt suggestions
  data, status_code, headers = api_instance.create_prompt_generation_with_http_info(prompt_generation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PromptGenerationResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->create_prompt_generation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompt_generation_request** | [**PromptGenerationRequest**](PromptGenerationRequest.md) |  |  |

### Return type

[**PromptGenerationResponse**](PromptGenerationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_prompts

> <PromptsCreateResponse> create_prompts(prompts_create_request)

Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. When the project does not run on the schedule (paused, or beyond the plan's project limit) the prompts are still created, and the response says so with `tracked` false, `untracked_reason` and a `warning`. Requires a `read_write` scope API key.

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


## get_prompt_generation

> <PromptGenerationResponse> get_prompt_generation(project_id, id)

Get a prompt generation run

Returns a run started with POST /prompt_generations: processing while the generator works, then completed with the suggestions it saved to the Suggested prompts queue, or failed with an error code and message. Poll every few seconds; most runs finish within a minute. Runs are kept for 24 hours, their suggestions stay in the queue.

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
id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # String | 

begin
  # Get a prompt generation run
  result = api_instance.get_prompt_generation(project_id, id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->get_prompt_generation: #{e}"
end
```

#### Using the get_prompt_generation_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PromptGenerationResponse>, Integer, Hash)> get_prompt_generation_with_http_info(project_id, id)

```ruby
begin
  # Get a prompt generation run
  data, status_code, headers = api_instance.get_prompt_generation_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PromptGenerationResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->get_prompt_generation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **String** |  |  |

### Return type

[**PromptGenerationResponse**](PromptGenerationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## import_prompts

> <PromptsImportResponse> import_prompts(prompts_import_request)

Import prompts

The app's CSV import as JSON: up to 500 rows, each with its own prompt, country_code, language_code (codes or names; both default to the project's) and tags, created when missing. Duplicates are skipped and existing prompts still get the row's tags. The prompt limits are checked before anything is written: when the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and imports nothing. A row is skipped and comes back in row_errors when its country or language is unknown, when it would give a prompt more than 50 tags (rows repeating a prompt add up) or when its tags would take the request past 500 new tags. For a team member without create access to Tags, a row that needs a tag that does not exist yet is skipped and comes back in row_errors. For a team member without update access to Prompts, a row matching a prompt that already existed adds no tags to it, and comes back in row_errors when it would have added one. Responds 201 when it created prompts, 200 otherwise. `tracked` false, with `untracked_reason` and a `warning`, means the project does not run on the schedule, so the imported prompts do not run until that changes. Requires a `read_write` scope API key and, for team members, create access to Prompts.

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
prompts_import_request = LLMPulse::PromptsImportRequest.new({project_id: 37, rows: [LLMPulse::PromptsImportRequestRowsInner.new({prompt: 'prompt_example'})]}) # PromptsImportRequest | 

begin
  # Import prompts
  result = api_instance.import_prompts(prompts_import_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->import_prompts: #{e}"
end
```

#### Using the import_prompts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PromptsImportResponse>, Integer, Hash)> import_prompts_with_http_info(prompts_import_request)

```ruby
begin
  # Import prompts
  data, status_code, headers = api_instance.import_prompts_with_http_info(prompts_import_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PromptsImportResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->import_prompts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompts_import_request** | [**PromptsImportRequest**](PromptsImportRequest.md) |  |  |

### Return type

[**PromptsImportResponse**](PromptsImportResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_prompt_executions

> <PromptExecutionsResponse> list_prompt_executions(project_id, opts)

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
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  mention_filter: 'mentions_you', # String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
  citation_filter: 'cites_you', # String | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
  competitors: 'competitors_example', # String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
  output: 'flat', # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand' # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
}

begin
  # List prompt executions
  result = api_instance.list_prompt_executions(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_prompt_executions: #{e}"
end
```

#### Using the list_prompt_executions_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PromptExecutionsResponse>, Integer, Hash)> list_prompt_executions_with_http_info(project_id, opts)

```ruby
begin
  # List prompt executions
  data, status_code, headers = api_instance.list_prompt_executions_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PromptExecutionsResponse>
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
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **mention_filter** | **String** | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] |
| **citation_filter** | **String** | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] |
| **competitors** | **String** | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |

### Return type

[**PromptExecutionsResponse**](PromptExecutionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_prompts

> <PromptsResponse> list_prompts(project_id, opts)

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
  model: 'chatgpt', # String | Keep only the prompts with at least one execution on this AI model, of any outcome and date (the prompts /dimensions/prompt_executions lists for the same model). Prompts have no model of their own, so a prompt with no execution on this model yet (a newly enabled model, or a locale the model does not cover) is left out. An unknown value, or a model the API key's user has not enabled, returns 422 ERR_INVALID_PARAM. from and to still filter prompt creation.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
  country_code: 'country_code_example', # String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
  language_code: 'language_code_example', # String | One ISO language code or a comma-separated list (e.g. en,es,de)
  prompt: 56, # Integer | Filter by prompt ID
  prompt_type: 'prompt_type_example', # String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
  brand_kind: 'brand', # String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List prompts
  result = api_instance.list_prompts(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_prompts: #{e}"
end
```

#### Using the list_prompts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PromptsResponse>, Integer, Hash)> list_prompts_with_http_info(project_id, opts)

```ruby
begin
  # List prompts
  data, status_code, headers = api_instance.list_prompts_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PromptsResponse>
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
| **model** | **String** | Keep only the prompts with at least one execution on this AI model, of any outcome and date (the prompts /dimensions/prompt_executions lists for the same model). Prompts have no model of their own, so a prompt with no execution on this model yet (a newly enabled model, or a locale the model does not cover) is left out. An unknown value, or a model the API key&#39;s user has not enabled, returns 422 ERR_INVALID_PARAM. from and to still filter prompt creation. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **country_code** | **String** | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **language_code** | **String** | One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer** | Filter by prompt ID | [optional] |
| **prompt_type** | **String** | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brand_kind** | **String** | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**PromptsResponse**](PromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


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
  model: 'chatgpt', # String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
  collection_id: '12,34', # String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
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
| **model** | **String** | Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] |
| **collection_id** | **String** | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
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


## list_suggested_prompts

> <SuggestedPromptsResponse> list_suggested_prompts(project_id, opts)

List suggested prompts

Lists the project's Suggested prompts queue, the same list the app's Suggested Prompts tab shows, oldest first. It holds the suggestions of every generator (website, magic for keyword runs, topic, reddit, paa, reputational, translate, gsc for Search Console, catalog). Pending suggestions by default; status=all also returns accepted (with the prompt they became) and rejected ones. Team members need create access to Prompts, like the app's tab.

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
  source: 'website', # String | Only suggestions from this generator
  status: 'pending', # String | Only suggestions in this status
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List suggested prompts
  result = api_instance.list_suggested_prompts(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_suggested_prompts: #{e}"
end
```

#### Using the list_suggested_prompts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuggestedPromptsResponse>, Integer, Hash)> list_suggested_prompts_with_http_info(project_id, opts)

```ruby
begin
  # List suggested prompts
  data, status_code, headers = api_instance.list_suggested_prompts_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuggestedPromptsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->list_suggested_prompts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **source** | **String** | Only suggestions from this generator | [optional] |
| **status** | **String** | Only suggestions in this status | [optional][default to &#39;pending&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 50] |

### Return type

[**SuggestedPromptsResponse**](SuggestedPromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## reject_suggested_prompts

> <SuggestedPromptsRejectResponse> reject_suggested_prompts(suggested_prompt_ids_request)

Reject suggested prompts

Marks up to 100 pending suggestions as rejected, so they leave the pending list; suggestions that are no longer pending stay as they are. Tracks and deletes nothing. Requires a `read_write` scope API key and, for team members, create access to Prompts.

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
suggested_prompt_ids_request = LLMPulse::SuggestedPromptIdsRequest.new({project_id: 37, ids: [37]}) # SuggestedPromptIdsRequest | 

begin
  # Reject suggested prompts
  result = api_instance.reject_suggested_prompts(suggested_prompt_ids_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->reject_suggested_prompts: #{e}"
end
```

#### Using the reject_suggested_prompts_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SuggestedPromptsRejectResponse>, Integer, Hash)> reject_suggested_prompts_with_http_info(suggested_prompt_ids_request)

```ruby
begin
  # Reject suggested prompts
  data, status_code, headers = api_instance.reject_suggested_prompts_with_http_info(suggested_prompt_ids_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SuggestedPromptsRejectResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->reject_suggested_prompts_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **suggested_prompt_ids_request** | [**SuggestedPromptIdsRequest**](SuggestedPromptIdsRequest.md) |  |  |

### Return type

[**SuggestedPromptsRejectResponse**](SuggestedPromptsRejectResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_prompt

> <PromptCategorizationResponse> update_prompt(id, update_prompt_request)

Edit a prompt's categorization

Manual categorization, exactly like editing the intent and brand badges on the prompt page: send `prompt_type`, `brand_kind` or both. The prompt is marked as manually categorized (`categorization_source` becomes `manual`), so automatic categorization no longer changes it; the prompt page can revert it to automatic. Any other field returns ERR_INVALID_PARAM. Not available from a white-label portal (ERR_INTEGRATION_UNAVAILABLE), where the page hides the editor. Requires a `read_write` scope API key and, for team members, update permission on Prompts.

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
id = 56 # Integer | 
update_prompt_request = LLMPulse::UpdatePromptRequest.new({project_id: 37}) # UpdatePromptRequest | 

begin
  # Edit a prompt's categorization
  result = api_instance.update_prompt(id, update_prompt_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->update_prompt: #{e}"
end
```

#### Using the update_prompt_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<PromptCategorizationResponse>, Integer, Hash)> update_prompt_with_http_info(id, update_prompt_request)

```ruby
begin
  # Edit a prompt's categorization
  data, status_code, headers = api_instance.update_prompt_with_http_info(id, update_prompt_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <PromptCategorizationResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->update_prompt_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **update_prompt_request** | [**UpdatePromptRequest**](UpdatePromptRequest.md) |  |  |

### Return type

[**PromptCategorizationResponse**](PromptCategorizationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


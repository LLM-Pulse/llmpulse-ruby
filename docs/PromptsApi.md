# LLMPulse::PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**assign_prompt_tags**](PromptsApi.md#assign_prompt_tags) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts |
| [**create_prompts**](PromptsApi.md#create_prompts) | **POST** /prompts | Bulk-create prompts |
| [**delete_prompt**](PromptsApi.md#delete_prompt) | **DELETE** /prompts/{id} | Delete a prompt |


## assign_prompt_tags

> assign_prompt_tags(assign_prompt_tags_request)

Bulk-attach tags to prompts

Idempotent bulk assignment of tags (Collections) to existing prompts. Tags can be resolved by id or by name (case-insensitive). Use `create_missing: true` to auto-create unknown tag names. Requires a `read_write` scope API key.

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
assign_prompt_tags_request = LLMPulse::AssignPromptTagsRequest.new({project_id: 37, prompt_ids: [37]}) # AssignPromptTagsRequest | 

begin
  # Bulk-attach tags to prompts
  api_instance.assign_prompt_tags(assign_prompt_tags_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->assign_prompt_tags: #{e}"
end
```

#### Using the assign_prompt_tags_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> assign_prompt_tags_with_http_info(assign_prompt_tags_request)

```ruby
begin
  # Bulk-attach tags to prompts
  data, status_code, headers = api_instance.assign_prompt_tags_with_http_info(assign_prompt_tags_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling PromptsApi->assign_prompt_tags_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **assign_prompt_tags_request** | [**AssignPromptTagsRequest**](AssignPromptTagsRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


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


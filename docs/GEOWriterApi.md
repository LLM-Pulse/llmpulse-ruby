# LLMPulse::GEOWriterApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_intelligence_task**](GEOWriterApi.md#create_intelligence_task) | **POST** /intelligence_tasks | Create a GEO Writer task |
| [**get_intelligence_task**](GEOWriterApi.md#get_intelligence_task) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task |
| [**list_intelligence_tasks**](GEOWriterApi.md#list_intelligence_tasks) | **GET** /intelligence_tasks | List GEO Writer tasks |
| [**revert_intelligence_task_content**](GEOWriterApi.md#revert_intelligence_task_content) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content |
| [**update_intelligence_task_content**](GEOWriterApi.md#update_intelligence_task_content) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content |


## create_intelligence_task

> <IntelligenceTask> create_intelligence_task(intelligence_task_create_request)

Create a GEO Writer task

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOWriterApi.new
intelligence_task_create_request = LLMPulse::IntelligenceTaskCreateRequest.new({project_id: 37, task_type: 'brief'}) # IntelligenceTaskCreateRequest | 

begin
  # Create a GEO Writer task
  result = api_instance.create_intelligence_task(intelligence_task_create_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->create_intelligence_task: #{e}"
end
```

#### Using the create_intelligence_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<IntelligenceTask>, Integer, Hash)> create_intelligence_task_with_http_info(intelligence_task_create_request)

```ruby
begin
  # Create a GEO Writer task
  data, status_code, headers = api_instance.create_intelligence_task_with_http_info(intelligence_task_create_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <IntelligenceTask>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->create_intelligence_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **intelligence_task_create_request** | [**IntelligenceTaskCreateRequest**](IntelligenceTaskCreateRequest.md) |  |  |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_intelligence_task

> <IntelligenceTask> get_intelligence_task(project_id, id)

Get a GEO Writer task

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOWriterApi.new
project_id = 56 # Integer | Project ID
id = 'id_example' # String | Numeric task ID or public_id string token

begin
  # Get a GEO Writer task
  result = api_instance.get_intelligence_task(project_id, id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->get_intelligence_task: #{e}"
end
```

#### Using the get_intelligence_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<IntelligenceTask>, Integer, Hash)> get_intelligence_task_with_http_info(project_id, id)

```ruby
begin
  # Get a GEO Writer task
  data, status_code, headers = api_instance.get_intelligence_task_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <IntelligenceTask>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->get_intelligence_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **String** | Numeric task ID or public_id string token |  |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_intelligence_tasks

> list_intelligence_tasks(project_id, opts)

List GEO Writer tasks

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOWriterApi.new
project_id = 56 # Integer | Project ID
opts = {
  task_type: 'brief', # String | 
  status: 'status_example', # String | 
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List GEO Writer tasks
  api_instance.list_intelligence_tasks(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->list_intelligence_tasks: #{e}"
end
```

#### Using the list_intelligence_tasks_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_intelligence_tasks_with_http_info(project_id, opts)

```ruby
begin
  # List GEO Writer tasks
  data, status_code, headers = api_instance.list_intelligence_tasks_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->list_intelligence_tasks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **task_type** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


## revert_intelligence_task_content

> <IntelligenceTask> revert_intelligence_task_content(project_id, id)

Revert GEO Writer task content

Discards every manual edit on the task and restores the output exactly as it was generated. Returns ERR_INVALID_PARAM when the task has no manual edits. Requires a `read_write` scope API key and, for team members, update permission on GEO Writer.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOWriterApi.new
project_id = 56 # Integer | Project ID
id = 'id_example' # String | Numeric task ID or public_id string token

begin
  # Revert GEO Writer task content
  result = api_instance.revert_intelligence_task_content(project_id, id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->revert_intelligence_task_content: #{e}"
end
```

#### Using the revert_intelligence_task_content_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<IntelligenceTask>, Integer, Hash)> revert_intelligence_task_content_with_http_info(project_id, id)

```ruby
begin
  # Revert GEO Writer task content
  data, status_code, headers = api_instance.revert_intelligence_task_content_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <IntelligenceTask>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->revert_intelligence_task_content_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **String** | Numeric task ID or public_id string token |  |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_intelligence_task_content

> <IntelligenceTaskUpdateResponse> update_intelligence_task_content(id, intelligence_task_update_request)

Edit GEO Writer task content

Edits the text of a completed task in place. `edits` maps dotted paths into result_data (for example `title` or `sections.0.content`) to replacement text. Only string fields that already exist can change: a path that does not resolve to text, a blank `title`, a value over 20,000 characters or an empty `edits` object is rejected with ERR_INVALID_PARAM and nothing is written. Values identical to the stored text are ignored, and the response lists the paths that actually changed. The first edit keeps a copy of the generated output so POST /intelligence_tasks/{id}/revert can restore it; regenerating the task replaces the edited content. Requires a `read_write` scope API key and, for team members, update permission on GEO Writer.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::GEOWriterApi.new
id = 'id_example' # String | Numeric task ID or public_id string token
intelligence_task_update_request = LLMPulse::IntelligenceTaskUpdateRequest.new({project_id: 37, edits: { key: 'inner_example'}}) # IntelligenceTaskUpdateRequest | 

begin
  # Edit GEO Writer task content
  result = api_instance.update_intelligence_task_content(id, intelligence_task_update_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->update_intelligence_task_content: #{e}"
end
```

#### Using the update_intelligence_task_content_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<IntelligenceTaskUpdateResponse>, Integer, Hash)> update_intelligence_task_content_with_http_info(id, intelligence_task_update_request)

```ruby
begin
  # Edit GEO Writer task content
  data, status_code, headers = api_instance.update_intelligence_task_content_with_http_info(id, intelligence_task_update_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <IntelligenceTaskUpdateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling GEOWriterApi->update_intelligence_task_content_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Numeric task ID or public_id string token |  |
| **intelligence_task_update_request** | [**IntelligenceTaskUpdateRequest**](IntelligenceTaskUpdateRequest.md) |  |  |

### Return type

[**IntelligenceTaskUpdateResponse**](IntelligenceTaskUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


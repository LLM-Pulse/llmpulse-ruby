# LLMPulse::CollectionsTagsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**assign_prompt_tags**](CollectionsTagsApi.md#assign_prompt_tags) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts |
| [**create_collection**](CollectionsTagsApi.md#create_collection) | **POST** /collections | Create a tag |
| [**delete_collection**](CollectionsTagsApi.md#delete_collection) | **DELETE** /collections/{id} | Delete a tag |
| [**list_collections**](CollectionsTagsApi.md#list_collections) | **GET** /dimensions/collections | List tags/collections |
| [**list_tags**](CollectionsTagsApi.md#list_tags) | **GET** /dimensions/tags | List tags (alias for /collections) |
| [**update_collection**](CollectionsTagsApi.md#update_collection) | **PATCH** /collections/{id} | Update a tag |


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

api_instance = LLMPulse::CollectionsTagsApi.new
assign_prompt_tags_request = LLMPulse::AssignPromptTagsRequest.new({project_id: 37, prompt_ids: [37]}) # AssignPromptTagsRequest | 

begin
  # Bulk-attach tags to prompts
  api_instance.assign_prompt_tags(assign_prompt_tags_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsTagsApi->assign_prompt_tags: #{e}"
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
  puts "Error when calling CollectionsTagsApi->assign_prompt_tags_with_http_info: #{e}"
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


## create_collection

> create_collection(create_collection_request)

Create a tag

Creates a tag (Collection) in a project. Optional `prompt_ids` attaches existing prompts in the same call. Tag name must be unique per project (case-insensitive). Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CollectionsTagsApi.new
create_collection_request = LLMPulse::CreateCollectionRequest.new({project_id: 37, name: 'name_example'}) # CreateCollectionRequest | 

begin
  # Create a tag
  api_instance.create_collection(create_collection_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsTagsApi->create_collection: #{e}"
end
```

#### Using the create_collection_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> create_collection_with_http_info(create_collection_request)

```ruby
begin
  # Create a tag
  data, status_code, headers = api_instance.create_collection_with_http_info(create_collection_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsTagsApi->create_collection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_collection_request** | [**CreateCollectionRequest**](CreateCollectionRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_collection

> delete_collection(project_id, id)

Delete a tag

Deletes a tag/collection. The prompts inside it are NOT deleted; only the grouping disappears. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CollectionsTagsApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 

begin
  # Delete a tag
  api_instance.delete_collection(project_id, id)
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsTagsApi->delete_collection: #{e}"
end
```

#### Using the delete_collection_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_collection_with_http_info(project_id, id)

```ruby
begin
  # Delete a tag
  data, status_code, headers = api_instance.delete_collection_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsTagsApi->delete_collection_with_http_info: #{e}"
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

api_instance = LLMPulse::CollectionsTagsApi.new
project_id = 56 # Integer | Project ID
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List tags/collections
  api_instance.list_collections(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsTagsApi->list_collections: #{e}"
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
  puts "Error when calling CollectionsTagsApi->list_collections_with_http_info: #{e}"
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

api_instance = LLMPulse::CollectionsTagsApi.new
project_id = 56 # Integer | Project ID
opts = {
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List tags (alias for /collections)
  api_instance.list_tags(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsTagsApi->list_tags: #{e}"
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
  puts "Error when calling CollectionsTagsApi->list_tags_with_http_info: #{e}"
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


## update_collection

> update_collection(id, update_collection_request)

Update a tag

Renames a tag/collection or changes its description. Prompt membership is managed via POST /prompts/assign_tags, not here. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CollectionsTagsApi.new
id = 56 # Integer | 
update_collection_request = LLMPulse::UpdateCollectionRequest.new({project_id: 37}) # UpdateCollectionRequest | 

begin
  # Update a tag
  api_instance.update_collection(id, update_collection_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsTagsApi->update_collection: #{e}"
end
```

#### Using the update_collection_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> update_collection_with_http_info(id, update_collection_request)

```ruby
begin
  # Update a tag
  data, status_code, headers = api_instance.update_collection_with_http_info(id, update_collection_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsTagsApi->update_collection_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **update_collection_request** | [**UpdateCollectionRequest**](UpdateCollectionRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


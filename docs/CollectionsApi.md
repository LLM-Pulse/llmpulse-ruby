# LLMPulse::CollectionsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_collection**](CollectionsApi.md#create_collection) | **POST** /collections | Create a tag |
| [**delete_collection**](CollectionsApi.md#delete_collection) | **DELETE** /collections/{id} | Delete a tag |
| [**update_collection**](CollectionsApi.md#update_collection) | **PATCH** /collections/{id} | Update a tag |


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

api_instance = LLMPulse::CollectionsApi.new
create_collection_request = LLMPulse::CreateCollectionRequest.new({project_id: 37, name: 'name_example'}) # CreateCollectionRequest | 

begin
  # Create a tag
  api_instance.create_collection(create_collection_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsApi->create_collection: #{e}"
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
  puts "Error when calling CollectionsApi->create_collection_with_http_info: #{e}"
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

api_instance = LLMPulse::CollectionsApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 

begin
  # Delete a tag
  api_instance.delete_collection(project_id, id)
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsApi->delete_collection: #{e}"
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
  puts "Error when calling CollectionsApi->delete_collection_with_http_info: #{e}"
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

api_instance = LLMPulse::CollectionsApi.new
id = 56 # Integer | 
update_collection_request = LLMPulse::UpdateCollectionRequest.new({project_id: 37}) # UpdateCollectionRequest | 

begin
  # Update a tag
  api_instance.update_collection(id, update_collection_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling CollectionsApi->update_collection: #{e}"
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
  puts "Error when calling CollectionsApi->update_collection_with_http_info: #{e}"
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


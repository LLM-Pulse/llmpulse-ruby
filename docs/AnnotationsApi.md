# LLMPulse::AnnotationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_annotation**](AnnotationsApi.md#create_annotation) | **POST** /annotations | Create a timeline annotation |
| [**delete_annotation**](AnnotationsApi.md#delete_annotation) | **DELETE** /annotations/{id} | Delete a timeline annotation |
| [**list_annotations**](AnnotationsApi.md#list_annotations) | **GET** /annotations | List timeline annotations |
| [**update_annotation**](AnnotationsApi.md#update_annotation) | **PATCH** /annotations/{id} | Update a timeline annotation |


## create_annotation

> create_annotation(create_annotation_request)

Create a timeline annotation

Marks a date in the project timeseries with a title + description. Requires the **Growth** plan or above. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AnnotationsApi.new
create_annotation_request = LLMPulse::CreateAnnotationRequest.new({project_id: 37, title: 'title_example'}) # CreateAnnotationRequest | 

begin
  # Create a timeline annotation
  api_instance.create_annotation(create_annotation_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling AnnotationsApi->create_annotation: #{e}"
end
```

#### Using the create_annotation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> create_annotation_with_http_info(create_annotation_request)

```ruby
begin
  # Create a timeline annotation
  data, status_code, headers = api_instance.create_annotation_with_http_info(create_annotation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling AnnotationsApi->create_annotation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_annotation_request** | [**CreateAnnotationRequest**](CreateAnnotationRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_annotation

> delete_annotation(project_id, id)

Delete a timeline annotation

Deletes an annotation. Same ownership rule as PATCH. Requires the **Growth** plan or above and a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AnnotationsApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 

begin
  # Delete a timeline annotation
  api_instance.delete_annotation(project_id, id)
rescue LLMPulse::ApiError => e
  puts "Error when calling AnnotationsApi->delete_annotation: #{e}"
end
```

#### Using the delete_annotation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_annotation_with_http_info(project_id, id)

```ruby
begin
  # Delete a timeline annotation
  data, status_code, headers = api_instance.delete_annotation_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling AnnotationsApi->delete_annotation_with_http_info: #{e}"
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


## list_annotations

> list_annotations(project_id, opts)

List timeline annotations

Lists the project timeline annotations (user-created + system), newest first. The category field tells them apart; editable says whether the requesting user may modify the row. Requires the **Growth** plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AnnotationsApi.new
project_id = 56 # Integer | Project ID
opts = {
  from: Date.parse('2013-10-20'), # Date | 
  to: Date.parse('2013-10-20'), # Date | 
  annotation_category_id: 56, # Integer | 
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List timeline annotations
  api_instance.list_annotations(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling AnnotationsApi->list_annotations: #{e}"
end
```

#### Using the list_annotations_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_annotations_with_http_info(project_id, opts)

```ruby
begin
  # List timeline annotations
  data, status_code, headers = api_instance.list_annotations_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling AnnotationsApi->list_annotations_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **from** | **Date** |  | [optional] |
| **to** | **Date** |  | [optional] |
| **annotation_category_id** | **Integer** |  | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_annotation

> update_annotation(id, update_annotation_request)

Update a timeline annotation

Updates title, description, annotation_date, color and/or annotation_category_id. Only user-created annotations belonging to the requesting user can be updated (system annotations never). Requires the **Growth** plan or above and a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::AnnotationsApi.new
id = 56 # Integer | 
update_annotation_request = LLMPulse::UpdateAnnotationRequest.new({project_id: 37}) # UpdateAnnotationRequest | 

begin
  # Update a timeline annotation
  api_instance.update_annotation(id, update_annotation_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling AnnotationsApi->update_annotation: #{e}"
end
```

#### Using the update_annotation_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> update_annotation_with_http_info(id, update_annotation_request)

```ruby
begin
  # Update a timeline annotation
  data, status_code, headers = api_instance.update_annotation_with_http_info(id, update_annotation_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling AnnotationsApi->update_annotation_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **update_annotation_request** | [**UpdateAnnotationRequest**](UpdateAnnotationRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


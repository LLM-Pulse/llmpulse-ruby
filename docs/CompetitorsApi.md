# LLMPulse::CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_competitor**](CompetitorsApi.md#create_competitor) | **POST** /competitors | Add a competitor |
| [**delete_competitor**](CompetitorsApi.md#delete_competitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**update_competitor**](CompetitorsApi.md#update_competitor) | **PATCH** /competitors/{id} | Update a competitor |


## create_competitor

> create_competitor(create_competitor_request)

Add a competitor

Adds a competitor (brand name + domain) to a project. Honours the per-plan max competitors cap. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CompetitorsApi.new
create_competitor_request = LLMPulse::CreateCompetitorRequest.new({project_id: 37, brand_name: 'brand_name_example', domain: 'domain_example'}) # CreateCompetitorRequest | 

begin
  # Add a competitor
  api_instance.create_competitor(create_competitor_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling CompetitorsApi->create_competitor: #{e}"
end
```

#### Using the create_competitor_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> create_competitor_with_http_info(create_competitor_request)

```ruby
begin
  # Add a competitor
  data, status_code, headers = api_instance.create_competitor_with_http_info(create_competitor_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling CompetitorsApi->create_competitor_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_competitor_request** | [**CreateCompetitorRequest**](CreateCompetitorRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_competitor

> delete_competitor(project_id, id)

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; its tracked data is purged by a background job. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CompetitorsApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 

begin
  # Delete a competitor
  api_instance.delete_competitor(project_id, id)
rescue LLMPulse::ApiError => e
  puts "Error when calling CompetitorsApi->delete_competitor: #{e}"
end
```

#### Using the delete_competitor_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_competitor_with_http_info(project_id, id)

```ruby
begin
  # Delete a competitor
  data, status_code, headers = api_instance.delete_competitor_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling CompetitorsApi->delete_competitor_with_http_info: #{e}"
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


## update_competitor

> update_competitor(id, update_competitor_request)

Update a competitor

Updates brand_name, matching_names (full replacement list; the brand name is always included automatically) and/or color. The domain is immutable after creation. Name changes re-run mention/citation matching in the background: the competitor shows processing=true for a few minutes and further edits are rejected meanwhile. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CompetitorsApi.new
id = 56 # Integer | 
update_competitor_request = LLMPulse::UpdateCompetitorRequest.new({project_id: 37}) # UpdateCompetitorRequest | 

begin
  # Update a competitor
  api_instance.update_competitor(id, update_competitor_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling CompetitorsApi->update_competitor: #{e}"
end
```

#### Using the update_competitor_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> update_competitor_with_http_info(id, update_competitor_request)

```ruby
begin
  # Update a competitor
  data, status_code, headers = api_instance.update_competitor_with_http_info(id, update_competitor_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling CompetitorsApi->update_competitor_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **update_competitor_request** | [**UpdateCompetitorRequest**](UpdateCompetitorRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


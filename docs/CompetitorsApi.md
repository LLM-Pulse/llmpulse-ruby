# LLMPulse::CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_competitor**](CompetitorsApi.md#create_competitor) | **POST** /competitors | Add a competitor |
| [**delete_competitor**](CompetitorsApi.md#delete_competitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**get_competitor_details**](CompetitorsApi.md#get_competitor_details) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**list_competitors**](CompetitorsApi.md#list_competitors) | **GET** /dimensions/competitors | List competitors |
| [**update_competitor**](CompetitorsApi.md#update_competitor) | **PATCH** /competitors/{id} | Update a competitor |


## create_competitor

> create_competitor(create_competitor_request)

Add a competitor

Adds a competitor with its own citation URL matching rule. Honours the per-plan max competitors cap. Requires a `read_write` scope API key.

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

api_instance = LLMPulse::CompetitorsApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | 

begin
  # Competitor details
  result = api_instance.get_competitor_details(project_id, id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling CompetitorsApi->get_competitor_details: #{e}"
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
  puts "Error when calling CompetitorsApi->get_competitor_details_with_http_info: #{e}"
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

api_instance = LLMPulse::CompetitorsApi.new
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
  puts "Error when calling CompetitorsApi->list_competitors: #{e}"
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
  puts "Error when calling CompetitorsApi->list_competitors_with_http_info: #{e}"
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


## update_competitor

> update_competitor(id, update_competitor_request)

Update a competitor

Updates brand_name, the competitor website domain or host, matching_names (full replacement list; the brand name is always included automatically), color and/or the citation URL matching rule. Website domain/host and citation-rule changes share one seven-day cooldown per competitor; other fields remain editable during the cooldown. Name, website or citation-rule changes re-run historical matching in the background: the competitor shows processing=true for a few minutes and further edits are rejected meanwhile. Requires a `read_write` scope API key.

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


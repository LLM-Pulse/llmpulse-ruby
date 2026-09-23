# LLMPulse::TechnicalGEOReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_technical_geo_reports**](TechnicalGEOReportsApi.md#create_technical_geo_reports) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**get_technical_geo_report**](TechnicalGEOReportsApi.md#get_technical_geo_report) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**list_technical_geo_reports**](TechnicalGEOReportsApi.md#list_technical_geo_reports) | **GET** /technical_geo_reports | List technical GEO reports |


## create_technical_geo_reports

> create_technical_geo_reports(create_technical_geo_reports_request)

Run technical GEO analysis

Launches the full technical GEO analysis bundle (crawlability, schema, content readiness, discoverability, site structure, robots.txt, agent readiness, llms.txt, AI visibility) for a URL + country. Each report runs in a background job. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::TechnicalGEOReportsApi.new
create_technical_geo_reports_request = LLMPulse::CreateTechnicalGeoReportsRequest.new({project_id: 37, url: 'url_example'}) # CreateTechnicalGeoReportsRequest | 

begin
  # Run technical GEO analysis
  api_instance.create_technical_geo_reports(create_technical_geo_reports_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->create_technical_geo_reports: #{e}"
end
```

#### Using the create_technical_geo_reports_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> create_technical_geo_reports_with_http_info(create_technical_geo_reports_request)

```ruby
begin
  # Run technical GEO analysis
  data, status_code, headers = api_instance.create_technical_geo_reports_with_http_info(create_technical_geo_reports_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->create_technical_geo_reports_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **create_technical_geo_reports_request** | [**CreateTechnicalGeoReportsRequest**](CreateTechnicalGeoReportsRequest.md) |  |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_technical_geo_report

> get_technical_geo_report(project_id, report_type, id)

Get a technical GEO report

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report left on the website's own language in the app, and for every other report type); a completed llms_txt result_data also returns manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, set once the customer edited the files in the app) and metadata.output_language_code.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::TechnicalGEOReportsApi.new
project_id = 56 # Integer | Project ID
report_type = 'crawlability' # String | 
id = 56 # Integer | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports

begin
  # Get a technical GEO report
  api_instance.get_technical_geo_report(project_id, report_type, id)
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->get_technical_geo_report: #{e}"
end
```

#### Using the get_technical_geo_report_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_technical_geo_report_with_http_info(project_id, report_type, id)

```ruby
begin
  # Get a technical GEO report
  data, status_code, headers = api_instance.get_technical_geo_report_with_http_info(project_id, report_type, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->get_technical_geo_report_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **report_type** | **String** |  |  |
| **id** | **Integer** | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports |  |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_technical_geo_reports

> list_technical_geo_reports(project_id, report_type, opts)

List technical GEO reports

Lists reports of one technical GEO type for a project, newest first. Use agent_readiness for the AI/Agent Readiness report.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::TechnicalGEOReportsApi.new
project_id = 56 # Integer | Project ID
report_type = 'crawlability' # String | 
opts = {
  status: 'status_example', # String | Optional status filter; valid values depend on report_type
  batch_id: 56, # Integer | Optional batch id returned when the report bundle was created
  page: 56, # Integer | 
  per_page: 56 # Integer | 
}

begin
  # List technical GEO reports
  api_instance.list_technical_geo_reports(project_id, report_type, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->list_technical_geo_reports: #{e}"
end
```

#### Using the list_technical_geo_reports_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> list_technical_geo_reports_with_http_info(project_id, report_type, opts)

```ruby
begin
  # List technical GEO reports
  data, status_code, headers = api_instance.list_technical_geo_reports_with_http_info(project_id, report_type, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->list_technical_geo_reports_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **report_type** | **String** |  |  |
| **status** | **String** | Optional status filter; valid values depend on report_type | [optional] |
| **batch_id** | **Integer** | Optional batch id returned when the report bundle was created | [optional] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


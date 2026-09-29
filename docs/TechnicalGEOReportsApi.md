# LLMPulse::TechnicalGEOReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_technical_geo_reports**](TechnicalGEOReportsApi.md#create_technical_geo_reports) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**get_technical_geo_report**](TechnicalGEOReportsApi.md#get_technical_geo_report) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**list_technical_geo_reports**](TechnicalGEOReportsApi.md#list_technical_geo_reports) | **GET** /technical_geo_reports | List technical GEO reports |
| [**revert_technical_geo_report_content**](TechnicalGEOReportsApi.md#revert_technical_geo_report_content) | **POST** /technical_geo_reports/{id}/revert_content | Revert llms.txt report content |
| [**update_technical_geo_report_content**](TechnicalGEOReportsApi.md#update_technical_geo_report_content) | **PATCH** /technical_geo_reports/{id}/content | Edit llms.txt report content |


## create_technical_geo_reports

> create_technical_geo_reports(create_technical_geo_reports_request)

Run technical GEO analysis

Launches the full nine-report technical GEO analysis bundle for a URL + country. The bundle starts only when at least nine daily units remain. Each successfully created report uses one unit; a report that is not created uses none. Daily allocations vary by account. Each report runs in a background job. Requires a `read_write` scope API key.

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

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website's own language, requested as auto or chosen in the app, and for every other report type); a completed llms_txt result_data also returns content_version (send it back to PATCH /technical_geo_reports/{id}/content), manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, kept from the first manual edit in the app, the API or MCP) and metadata.output_language_code.

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


## revert_technical_geo_report_content

> <LlmsTxtTechnicalGeoReport> revert_technical_geo_report_content(id, technical_geo_report_content_revert_request)

Revert llms.txt report content

Discards every manual edit on the llms_txt report and restores the llms.txt and llms-full.txt files exactly as they were generated. Returns ERR_INVALID_PARAM when the report has no manual edits or report_type is not llms_txt. Requires a `read_write` scope API key and, for team members, create permission on GEO Optimization.

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
id = 56 # Integer | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
technical_geo_report_content_revert_request = LLMPulse::TechnicalGeoReportContentRevertRequest.new({project_id: 37, report_type: 'llms_txt'}) # TechnicalGeoReportContentRevertRequest | 

begin
  # Revert llms.txt report content
  result = api_instance.revert_technical_geo_report_content(id, technical_geo_report_content_revert_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->revert_technical_geo_report_content: #{e}"
end
```

#### Using the revert_technical_geo_report_content_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<LlmsTxtTechnicalGeoReport>, Integer, Hash)> revert_technical_geo_report_content_with_http_info(id, technical_geo_report_content_revert_request)

```ruby
begin
  # Revert llms.txt report content
  data, status_code, headers = api_instance.revert_technical_geo_report_content_with_http_info(id, technical_geo_report_content_revert_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <LlmsTxtTechnicalGeoReport>
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->revert_technical_geo_report_content_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports |  |
| **technical_geo_report_content_revert_request** | [**TechnicalGeoReportContentRevertRequest**](TechnicalGeoReportContentRevertRequest.md) |  |  |

### Return type

[**LlmsTxtTechnicalGeoReport**](LlmsTxtTechnicalGeoReport.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_technical_geo_report_content

> <TechnicalGeoReportContentUpdateResponse> update_technical_geo_report_content(id, technical_geo_report_content_update_request)

Edit llms.txt report content

Replaces the llms.txt and llms-full.txt files of a completed llms_txt report in place, without generating them again. `edits` maps llms_txt and/or llms_full_txt to the full replacement text. `content_version` must equal result_data.content_version of the report as last read; when the report changed since, the edit is refused as stale and the message names the current version. A missing or stale content_version, a blank file, a file over 200,000 characters, a value that is not text, an unknown file key, an empty `edits` object, a report that has not completed or a report_type other than llms_txt is rejected with ERR_INVALID_PARAM and nothing is written. Files are stored with Unix line endings and one trailing newline. A file identical to the stored one is ignored, and the response lists the files that actually changed. The first edit keeps the generated files in original_llms_txt_content and original_llms_full_txt_content so POST /technical_geo_reports/{id}/revert_content can restore them; running the report again creates a new report without these edits. Requires a `read_write` scope API key and, for team members, create permission on GEO Optimization.

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
id = 56 # Integer | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
technical_geo_report_content_update_request = LLMPulse::TechnicalGeoReportContentUpdateRequest.new({project_id: 37, report_type: 'llms_txt', content_version: '1790683200123456', edits: LLMPulse::TechnicalGeoReportContentUpdateRequestEdits.new}) # TechnicalGeoReportContentUpdateRequest | 

begin
  # Edit llms.txt report content
  result = api_instance.update_technical_geo_report_content(id, technical_geo_report_content_update_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->update_technical_geo_report_content: #{e}"
end
```

#### Using the update_technical_geo_report_content_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<TechnicalGeoReportContentUpdateResponse>, Integer, Hash)> update_technical_geo_report_content_with_http_info(id, technical_geo_report_content_update_request)

```ruby
begin
  # Edit llms.txt report content
  data, status_code, headers = api_instance.update_technical_geo_report_content_with_http_info(id, technical_geo_report_content_update_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <TechnicalGeoReportContentUpdateResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling TechnicalGEOReportsApi->update_technical_geo_report_content_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports |  |
| **technical_geo_report_content_update_request** | [**TechnicalGeoReportContentUpdateRequest**](TechnicalGeoReportContentUpdateRequest.md) |  |  |

### Return type

[**TechnicalGeoReportContentUpdateResponse**](TechnicalGeoReportContentUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


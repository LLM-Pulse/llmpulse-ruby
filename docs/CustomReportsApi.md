# LLMPulse::CustomReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_custom_report**](CustomReportsApi.md#get_custom_report) | **GET** /custom_reports/{id} | Get a custom report with its widget data |
| [**list_custom_reports**](CustomReportsApi.md#list_custom_reports) | **GET** /custom_reports | List custom reports |
| [**send_custom_report**](CustomReportsApi.md#send_custom_report) | **POST** /custom_reports/{id}/send | Send a custom report now |


## get_custom_report

> <CustomReportDetailResponse> get_custom_report(project_id, id)

Get a custom report with its widget data

The configuration of one custom report (date range, filters, schedule, layout) and the data of every widget computed for today, the same numbers the report page, its shared link and its PDF show. Each widget carries its `kind` and a `data` object shaped by it: `series` for `timeseries`, `slices` for `donut`, `bars` for `bar`, `values` and `changes` for `kpi_grid`, `rows` for `table`. A widget whose data source is not connected has `available: false` and `data: null`. Nothing is saved or sent. Requires the Scale plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CustomReportsApi.new
project_id = 56 # Integer | Project ID
id = 56 # Integer | Custom report id, from GET /custom_reports

begin
  # Get a custom report with its widget data
  result = api_instance.get_custom_report(project_id, id)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling CustomReportsApi->get_custom_report: #{e}"
end
```

#### Using the get_custom_report_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CustomReportDetailResponse>, Integer, Hash)> get_custom_report_with_http_info(project_id, id)

```ruby
begin
  # Get a custom report with its widget data
  data, status_code, headers = api_instance.get_custom_report_with_http_info(project_id, id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CustomReportDetailResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling CustomReportsApi->get_custom_report_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **id** | **Integer** | Custom report id, from GET /custom_reports |  |

### Return type

[**CustomReportDetailResponse**](CustomReportDetailResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_custom_reports

> <CustomReportsResponse> list_custom_reports(project_id, opts)

List custom reports

The custom reports of the project, newest first, as the Reports > Custom Reports list shows them. Recipient addresses, the shared-link token and the password are never returned. Requires the Scale plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CustomReportsApi.new
project_id = 56 # Integer | Project ID
opts = {
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # List custom reports
  result = api_instance.list_custom_reports(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling CustomReportsApi->list_custom_reports: #{e}"
end
```

#### Using the list_custom_reports_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CustomReportsResponse>, Integer, Hash)> list_custom_reports_with_http_info(project_id, opts)

```ruby
begin
  # List custom reports
  data, status_code, headers = api_instance.list_custom_reports_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CustomReportsResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling CustomReportsApi->list_custom_reports_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**CustomReportsResponse**](CustomReportsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## send_custom_report

> <CustomReportSendResponse> send_custom_report(id, send_custom_report_request)

Send a custom report now

Queues the report's PDF for its recipients, like the Send now button on the report page: the report must be published and have at least one recipient (ERR_INVALID_PARAM otherwise), and each report can be sent once every 10 minutes (429 ERR_RATE_LIMITED with Retry-After). Not available from a white-label portal or for a report made inside one (ERR_INTEGRATION_UNAVAILABLE). Requires the Scale plan or above, a `read_write` scope API key and, for team members, update permission on Custom Reports.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::CustomReportsApi.new
id = 56 # Integer | Custom report id, from GET /custom_reports
send_custom_report_request = LLMPulse::SendCustomReportRequest.new({project_id: 37}) # SendCustomReportRequest | 

begin
  # Send a custom report now
  result = api_instance.send_custom_report(id, send_custom_report_request)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling CustomReportsApi->send_custom_report: #{e}"
end
```

#### Using the send_custom_report_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CustomReportSendResponse>, Integer, Hash)> send_custom_report_with_http_info(id, send_custom_report_request)

```ruby
begin
  # Send a custom report now
  data, status_code, headers = api_instance.send_custom_report_with_http_info(id, send_custom_report_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CustomReportSendResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling CustomReportsApi->send_custom_report_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | Custom report id, from GET /custom_reports |  |
| **send_custom_report_request** | [**SendCustomReportRequest**](SendCustomReportRequest.md) |  |  |

### Return type

[**CustomReportSendResponse**](CustomReportSendResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


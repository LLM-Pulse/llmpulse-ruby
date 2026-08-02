# LLMPulse::SearchConsoleApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_search_console_pages**](SearchConsoleApi.md#get_search_console_pages) | **GET** /search_console/pages | Top Search Console pages (Growth+) |
| [**get_search_console_queries**](SearchConsoleApi.md#get_search_console_queries) | **GET** /search_console/queries | Top Search Console queries (Growth+) |
| [**get_search_console_summary**](SearchConsoleApi.md#get_search_console_summary) | **GET** /search_console/summary | Search Console summary (Growth+) |
| [**get_search_console_timeseries**](SearchConsoleApi.md#get_search_console_timeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+) |


## get_search_console_pages

> get_search_console_pages(project_id, opts)

Top Search Console pages (Growth+)

Top Google Search Console landing pages over a date range, ranked by impressions, clicks, ctr or position, paginated. Requires a connected Search Console property (Growth+).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  sort: 'impressions', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Top Search Console pages (Growth+)
  api_instance.get_search_console_pages(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_pages: #{e}"
end
```

#### Using the get_search_console_pages_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_search_console_pages_with_http_info(project_id, opts)

```ruby
begin
  # Top Search Console pages (Growth+)
  data, status_code, headers = api_instance.get_search_console_pages_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_pages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **sort** | **String** |  | [optional][default to &#39;impressions&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_queries

> get_search_console_queries(project_id, opts)

Top Search Console queries (Growth+)

Top Google Search Console search queries over a date range, ranked by impressions, clicks, ctr or position, paginated. Knowingly undercounts anonymized queries; for exact totals use /search_console/summary. Requires a connected Search Console property (Growth+).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  sort: 'impressions', # String | 
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Top Search Console queries (Growth+)
  api_instance.get_search_console_queries(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_queries: #{e}"
end
```

#### Using the get_search_console_queries_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_search_console_queries_with_http_info(project_id, opts)

```ruby
begin
  # Top Search Console queries (Growth+)
  data, status_code, headers = api_instance.get_search_console_queries_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_queries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **sort** | **String** |  | [optional][default to &#39;impressions&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_summary

> get_search_console_summary(project_id, opts)

Search Console summary (Growth+)

Google Search Console headline totals (impressions, clicks, ctr as a 0..1 fraction, average position) for the project over a date range. Pass dimension=country or dimension=device to also receive the breakdown aggregated over the range. Requires the project to have a connected Search Console property and the Growth plan or above; otherwise returns ERR_SEARCH_CONSOLE_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  dimension: 'country' # String | Optional breakdown aggregated over the range
}

begin
  # Search Console summary (Growth+)
  api_instance.get_search_console_summary(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_summary: #{e}"
end
```

#### Using the get_search_console_summary_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_search_console_summary_with_http_info(project_id, opts)

```ruby
begin
  # Search Console summary (Growth+)
  data, status_code, headers = api_instance.get_search_console_summary_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_summary_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **dimension** | **String** | Optional breakdown aggregated over the range | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_search_console_timeseries

> get_search_console_timeseries(project_id, opts)

Search Console time series (Growth+)

Google Search Console property-wide series (impressions, clicks, ctr, position) bucketed by day, week or month. Requires a connected Search Console property (Growth+).

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::SearchConsoleApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back (alternative to from/to)
  from: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  to: Time.parse('2013-10-20T19:20:30+01:00'), # Time | 
  granularity: 'day', # String | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Search Console time series (Growth+)
  api_instance.get_search_console_timeseries(project_id, opts)
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_timeseries: #{e}"
end
```

#### Using the get_search_console_timeseries_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> get_search_console_timeseries_with_http_info(project_id, opts)

```ruby
begin
  # Search Console time series (Growth+)
  data, status_code, headers = api_instance.get_search_console_timeseries_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue LLMPulse::ApiError => e
  puts "Error when calling SearchConsoleApi->get_search_console_timeseries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back (alternative to from/to) | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **granularity** | **String** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

nil (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


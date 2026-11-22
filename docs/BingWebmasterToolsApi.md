# LLMPulse::BingWebmasterToolsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_bing_webmaster_pages**](BingWebmasterToolsApi.md#get_bing_webmaster_pages) | **GET** /bing_webmaster/pages | Top Bing Webmaster Tools pages (Growth+) |
| [**get_bing_webmaster_queries**](BingWebmasterToolsApi.md#get_bing_webmaster_queries) | **GET** /bing_webmaster/queries | Top Bing Webmaster Tools queries (Growth+) |
| [**get_bing_webmaster_summary**](BingWebmasterToolsApi.md#get_bing_webmaster_summary) | **GET** /bing_webmaster/summary | Bing Webmaster Tools summary (Growth+) |
| [**get_bing_webmaster_timeseries**](BingWebmasterToolsApi.md#get_bing_webmaster_timeseries) | **GET** /bing_webmaster/timeseries | Bing Webmaster Tools time series (Growth+) |


## get_bing_webmaster_pages

> <BingWebmasterListResponse> get_bing_webmaster_pages(project_id, opts)

Top Bing Webmaster Tools pages (Growth+)

The landing pages of the project's connected Bing Webmaster Tools site in Bing Search, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top pages of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::BingWebmasterToolsApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
  sort: 'impressions', # String | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Top Bing Webmaster Tools pages (Growth+)
  result = api_instance.get_bing_webmaster_pages(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling BingWebmasterToolsApi->get_bing_webmaster_pages: #{e}"
end
```

#### Using the get_bing_webmaster_pages_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BingWebmasterListResponse>, Integer, Hash)> get_bing_webmaster_pages_with_http_info(project_id, opts)

```ruby
begin
  # Top Bing Webmaster Tools pages (Growth+)
  data, status_code, headers = api_instance.get_bing_webmaster_pages_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BingWebmasterListResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling BingWebmasterToolsApi->get_bing_webmaster_pages_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **String** | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional][default to &#39;impressions&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**BingWebmasterListResponse**](BingWebmasterListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_bing_webmaster_queries

> <BingWebmasterListResponse> get_bing_webmaster_queries(project_id, opts)

Top Bing Webmaster Tools queries (Growth+)

The Bing search queries of the project's connected Bing Webmaster Tools site, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top queries of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::BingWebmasterToolsApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
  sort: 'impressions', # String | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
  page: 56, # Integer | 
  per_page: 56, # Integer | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Top Bing Webmaster Tools queries (Growth+)
  result = api_instance.get_bing_webmaster_queries(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling BingWebmasterToolsApi->get_bing_webmaster_queries: #{e}"
end
```

#### Using the get_bing_webmaster_queries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BingWebmasterListResponse>, Integer, Hash)> get_bing_webmaster_queries_with_http_info(project_id, opts)

```ruby
begin
  # Top Bing Webmaster Tools queries (Growth+)
  data, status_code, headers = api_instance.get_bing_webmaster_queries_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BingWebmasterListResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling BingWebmasterToolsApi->get_bing_webmaster_queries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **String** | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional][default to &#39;impressions&#39;] |
| **page** | **Integer** |  | [optional][default to 1] |
| **per_page** | **Integer** |  | [optional][default to 20] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**BingWebmasterListResponse**](BingWebmasterListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_bing_webmaster_summary

> <BingWebmasterSummaryResponse> get_bing_webmaster_summary(project_id, opts)

Bing Webmaster Tools summary (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project's connected Bing Webmaster Tools site over a date range, summed from the daily site totals synced once a day. Bing reports no average position in its daily totals. About 13 months of history are kept; data_through is the last day synced, and later days are missing, not zero. history_current is false right after the site was changed in Preferences > Project Settings > Connections and before its first sync: the totals are then zero and data_through and last_synced_at null. A connection whose sync_status is on_hold (Bing refused the stored API key, or the site is no longer verified) still answers from the data already synced. Requires a connected Bing Webmaster Tools site and the Growth plan or above; otherwise returns ERR_BING_WEBMASTER_NOT_CONNECTED (with meta.connect_url) or ERR_PLAN_REQUIRED.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::BingWebmasterToolsApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
  to: Date.parse('2013-10-20') # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
}

begin
  # Bing Webmaster Tools summary (Growth+)
  result = api_instance.get_bing_webmaster_summary(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling BingWebmasterToolsApi->get_bing_webmaster_summary: #{e}"
end
```

#### Using the get_bing_webmaster_summary_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BingWebmasterSummaryResponse>, Integer, Hash)> get_bing_webmaster_summary_with_http_info(project_id, opts)

```ruby
begin
  # Bing Webmaster Tools summary (Growth+)
  data, status_code, headers = api_instance.get_bing_webmaster_summary_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BingWebmasterSummaryResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling BingWebmasterToolsApi->get_bing_webmaster_summary_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |

### Return type

[**BingWebmasterSummaryResponse**](BingWebmasterSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_bing_webmaster_timeseries

> <BingWebmasterTimeseriesResponse> get_bing_webmaster_timeseries(project_id, opts)

Bing Webmaster Tools time series (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project's connected Bing Webmaster Tools site, bucketed by day, week (starting Monday) or month from the daily site totals synced once a day. Days without synced data are left out of the series, not reported as zero. Bing reports no average position in its daily totals. About 13 months of history are kept. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::BingWebmasterToolsApi.new
project_id = 56 # Integer | Project ID
opts = {
  range: 56, # Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
  from: Date.parse('2013-10-20'), # Date | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
  to: Date.parse('2013-10-20'), # Date | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
  granularity: 'day', # String | 
  output: 'flat' # String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
}

begin
  # Bing Webmaster Tools time series (Growth+)
  result = api_instance.get_bing_webmaster_timeseries(project_id, opts)
  p result
rescue LLMPulse::ApiError => e
  puts "Error when calling BingWebmasterToolsApi->get_bing_webmaster_timeseries: #{e}"
end
```

#### Using the get_bing_webmaster_timeseries_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<BingWebmasterTimeseriesResponse>, Integer, Hash)> get_bing_webmaster_timeseries_with_http_info(project_id, opts)

```ruby
begin
  # Bing Webmaster Tools time series (Growth+)
  data, status_code, headers = api_instance.get_bing_webmaster_timeseries_with_http_info(project_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <BingWebmasterTimeseriesResponse>
rescue LLMPulse::ApiError => e
  puts "Error when calling BingWebmasterToolsApi->get_bing_webmaster_timeseries_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** | Project ID |  |
| **range** | **Integer** | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **Date** | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **Date** | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **granularity** | **String** |  | [optional] |
| **output** | **String** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] |

### Return type

[**BingWebmasterTimeseriesResponse**](BingWebmasterTimeseriesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


# LLMPulse::ReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_technical_geo_reports**](ReportsApi.md#create_technical_geo_reports) | **POST** /technical_geo_reports | Run technical GEO analysis |


## create_technical_geo_reports

> create_technical_geo_reports(create_technical_geo_reports_request)

Run technical GEO analysis

Launches the full technical GEO analysis bundle (crawlability, schema, content readiness, discoverability, site structure, robots.txt, llms.txt, AI visibility) for a URL + country. Each report runs in a background job. Requires a `read_write` scope API key.

### Examples

```ruby
require 'time'
require 'llmpulse'
# setup authorization
LLMPulse.configure do |config|
  # Configure Bearer authorization: BearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = LLMPulse::ReportsApi.new
create_technical_geo_reports_request = LLMPulse::CreateTechnicalGeoReportsRequest.new({project_id: 37, url: 'url_example'}) # CreateTechnicalGeoReportsRequest | 

begin
  # Run technical GEO analysis
  api_instance.create_technical_geo_reports(create_technical_geo_reports_request)
rescue LLMPulse::ApiError => e
  puts "Error when calling ReportsApi->create_technical_geo_reports: #{e}"
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
  puts "Error when calling ReportsApi->create_technical_geo_reports_with_http_info: #{e}"
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


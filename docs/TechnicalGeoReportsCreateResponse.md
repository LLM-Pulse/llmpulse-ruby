# LLMPulse::TechnicalGeoReportsCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **url** | **String** | The URL analysed |  |
| **country_code** | **String** | The country used, the project country when none was sent |  |
| **output_language_code** | **String** | ISO 639-1 code the llms.txt files are written in, or auto for the website&#39;s own language |  |
| **batch_id** | **Integer** | Bundle id, for the batch_id filter of GET /technical_geo_reports; null when no report was created |  |
| **created_reports** | **Array&lt;String&gt;** | The report_type of every report created |  |
| **report_ids** | **Hash&lt;String, Integer&gt;** | The id of each created report, by report_type |  |
| **app_urls** | **Hash&lt;String, String&gt;** | The link that opens each created report in the app, by report_type |  |
| **failed_reports** | [**Array&lt;TechnicalGeoReportsCreateResponseFailedReportsInner&gt;**](TechnicalGeoReportsCreateResponseFailedReportsInner.md) | Reports that could not be created, with the reasons |  |
| **next_endpoint** | **String** | Path template to poll each created report |  |
| **poll_after_seconds** | **Integer** | Seconds to wait before the first poll |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TechnicalGeoReportsCreateResponse.new(
  project_id: null,
  url: null,
  country_code: null,
  output_language_code: null,
  batch_id: null,
  created_reports: null,
  report_ids: null,
  app_urls: null,
  failed_reports: null,
  next_endpoint: null,
  poll_after_seconds: null,
  request_id: null
)
```


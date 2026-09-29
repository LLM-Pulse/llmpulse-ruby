# LLMPulse::LlmsTxtTechnicalGeoReport

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **report_type** | **String** | Always llms_txt | [optional] |
| **project_id** | **Integer** |  | [optional] |
| **batch_id** | **Integer** | Bundle the report was created in; null for a report created on its own | [optional] |
| **url** | **String** | Always null for llms_txt reports; domain names the website | [optional] |
| **domain** | **String** |  | [optional] |
| **country_code** | **String** |  | [optional] |
| **output_language_code** | **String** | ISO 639-1 code the files were requested in; null when they are written in the website&#39;s own language | [optional] |
| **status** | **String** |  | [optional] |
| **result_available** | **Boolean** |  | [optional] |
| **overall_score** | **Float** | Always null for llms_txt reports | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |
| **result_data** | [**LlmsTxtTechnicalGeoReportResultData**](LlmsTxtTechnicalGeoReportResultData.md) |  | [optional] |
| **error_message** | **String** |  | [optional] |
| **poll_after_seconds** | **Integer** | Seconds to wait before polling again while the report runs; null once it has finished | [optional] |
| **app_url** | **String** | Opens this report in the app | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::LlmsTxtTechnicalGeoReport.new(
  id: null,
  report_type: null,
  project_id: null,
  batch_id: null,
  url: null,
  domain: null,
  country_code: null,
  output_language_code: null,
  status: null,
  result_available: null,
  overall_score: null,
  created_at: null,
  updated_at: null,
  result_data: null,
  error_message: null,
  poll_after_seconds: null,
  app_url: null,
  request_id: null
)
```


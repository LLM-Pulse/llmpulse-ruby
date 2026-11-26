# LLMPulse::TechnicalGeoReportSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **report_type** | **String** | The report_type requested (agent_readiness for ai_readiness) |  |
| **project_id** | **Integer** |  |  |
| **batch_id** | **Integer** | Bundle the report was created in; null for a report created on its own |  |
| **url** | **String** | The page analysed; null for the domain-level types (robots_txt, agent_readiness, llms_txt, ai_visibility) |  |
| **domain** | **String** |  |  |
| **country_code** | **String** | Set only on llms_txt and ai_visibility reports |  |
| **output_language_code** | **String** | ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website&#39;s own language and for every other type |  |
| **status** | **String** | Depends on report_type. Every type ends completed or failed; ai_visibility can also end insufficient_data |  |
| **result_available** | **Boolean** | Whether status is completed |  |
| **overall_score** | **Float** | Null until the report completes, and always for llms_txt |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **app_url** | **String** | Opens this report in the app | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TechnicalGeoReportSummary.new(
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
  app_url: null
)
```


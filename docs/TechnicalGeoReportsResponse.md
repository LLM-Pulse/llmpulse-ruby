# LLMPulse::TechnicalGeoReportsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **report_type** | **String** | The report_type requested (agent_readiness for ai_readiness) |  |
| **data** | [**Array&lt;TechnicalGeoReportSummary&gt;**](TechnicalGeoReportSummary.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TechnicalGeoReportsResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  report_type: null,
  data: null
)
```


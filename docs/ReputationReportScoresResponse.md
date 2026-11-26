# LLMPulse::ReputationReportScoresResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **report** | [**ReputationReportSummary**](ReputationReportSummary.md) |  |  |
| **data** | [**Array&lt;AnalystScoreRow&gt;**](AnalystScoreRow.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ReputationReportScoresResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  report: null,
  data: null
)
```


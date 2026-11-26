# LLMPulse::StudyReportScoresResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **study_id** | **Integer** |  |  |
| **report** | [**ReputationReportSummary**](ReputationReportSummary.md) |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Score rows matching the filters across every page |  |
| **data** | [**Array&lt;AnalystScoreRow&gt;**](AnalystScoreRow.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::StudyReportScoresResponse.new(
  study_id: null,
  report: null,
  page: null,
  per_page: null,
  total: null,
  data: null,
  request_id: null
)
```


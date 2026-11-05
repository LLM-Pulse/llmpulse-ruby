# LLMPulse::ReputationReportCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **created** | **Boolean** | True when this request started a new report; false when it returned the one that already holds the month |  |
| **report** | [**ReputationReportSummary**](ReputationReportSummary.md) |  |  |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ReputationReportCreateResponse.new(
  project_id: null,
  created: null,
  report: null,
  request_id: null
)
```


# LLMPulse::AiModelInsightsSummaryResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **filters** | [**AiModelInsightsFiltersEcho**](AiModelInsightsFiltersEcho.md) |  | [optional] |
| **models** | [**Array&lt;AiModelInsightsModel&gt;**](AiModelInsightsModel.md) | The AI models the account has enabled or that answered in the window, in the in-app column order | [optional] |
| **summary** | [**AiModelInsightsSummaryResponseSummary**](AiModelInsightsSummaryResponseSummary.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelInsightsSummaryResponse.new(
  project_id: null,
  from: null,
  to: null,
  filters: null,
  models: null,
  summary: null,
  request_id: null
)
```


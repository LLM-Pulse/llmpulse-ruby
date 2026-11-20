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
| **plan_required_fields** | **Array&lt;String&gt;** | The summary sections left out because they need a higher plan (brand_net_sentiment_by_model and sentiment_market_share below Growth); empty when none is |  |
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
  plan_required_fields: null,
  request_id: null
)
```


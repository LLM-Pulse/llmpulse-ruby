# LLMPulse::AiModelInsightsSummaryResponseSummaryBrandNetSentimentByModel

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_sentiments** | **Integer** | Brand sentiment verdicts across the models | [optional] |
| **models** | [**Array&lt;AiModelSentimentRow&gt;**](AiModelSentimentRow.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelInsightsSummaryResponseSummaryBrandNetSentimentByModel.new(
  total_sentiments: null,
  models: null
)
```


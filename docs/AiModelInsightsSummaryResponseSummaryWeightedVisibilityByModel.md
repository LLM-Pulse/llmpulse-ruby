# LLMPulse::AiModelInsightsSummaryResponseSummaryWeightedVisibilityByModel

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_weighted_visibility_score** | **Float** | The brand&#39;s AI Visibility Score points across the models; 0 when it has none | [optional] |
| **models** | [**Array&lt;AiModelWeightedVisibilityRow&gt;**](AiModelWeightedVisibilityRow.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelInsightsSummaryResponseSummaryWeightedVisibilityByModel.new(
  total_weighted_visibility_score: null,
  models: null
)
```


# LLMPulse::CitationSeries

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **granularity** | **String** |  |  |
| **total** | **Integer** | Equal to total_responses |  |
| **by_model** | **Hash&lt;String, Integer&gt;** | Answers per AI model, keyed by model, largest first |  |
| **data** | [**Array&lt;AiModelPositionDistributionBrandBucketsInnerDataInner&gt;**](AiModelPositionDistributionBrandBucketsInnerDataInner.md) | One point per period holding a filtered answer, oldest first; a zero means answers ran and none cited it |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationSeries.new(
  granularity: null,
  total: null,
  by_model: null,
  data: null
)
```


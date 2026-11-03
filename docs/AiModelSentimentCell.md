# LLMPulse::AiModelSentimentCell

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **value** | **Float** | The actor&#39;s net sentiment in the model, positive_count minus negative_count as a percentage (-100 to 100) of total_sentiments; null when total_sentiments is 0 | [optional] |
| **total_sentiments** | **Integer** | The actor&#39;s sentiment verdicts in the model&#39;s answers | [optional] |
| **positive_count** | **Integer** | Positive and very positive verdicts | [optional] |
| **negative_count** | **Integer** | Negative and very negative verdicts | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelSentimentCell.new(
  value: null,
  total_sentiments: null,
  positive_count: null,
  negative_count: null
)
```


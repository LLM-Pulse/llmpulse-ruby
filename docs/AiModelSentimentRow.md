# LLMPulse::AiModelSentimentRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **model** | **String** | AI model key, as /dimensions/models lists it | [optional] |
| **label** | **String** | Display name of the model | [optional] |
| **color** | **String** | Hex color the app charts the model with | [optional] |
| **sentiments_count** | **Integer** | Brand sentiment verdicts in the model&#39;s answers | [optional] |
| **positive_count** | **Integer** | Positive and very positive verdicts | [optional] |
| **negative_count** | **Integer** | Negative and very negative verdicts | [optional] |
| **net_sentiment** | **Float** | positive_count minus negative_count as a percentage (-100 to 100) of sentiments_count, neutral verdicts counted in the base; null when sentiments_count is 0 | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelSentimentRow.new(
  model: null,
  label: null,
  color: null,
  sentiments_count: null,
  positive_count: null,
  negative_count: null,
  net_sentiment: null
)
```


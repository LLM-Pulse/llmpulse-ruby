# LLMPulse::SentimentCategory

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **metric** | **String** | The metric key of the level (sentiment_&lt;key&gt;) |  |
| **key** | **String** | very_positive, positive, neutral, negative or very_negative |  |
| **label** | **String** |  |  |
| **color** | **String** | Hex color the app shows the level in |  |
| **score** | **Float** | Score of the level, from -1.0 (very_negative) to 1.0 (very_positive) |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SentimentCategory.new(
  metric: null,
  key: null,
  label: null,
  color: null,
  score: null
)
```


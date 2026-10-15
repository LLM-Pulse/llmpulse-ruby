# LLMPulse::SentimentBreakdownCounts

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mentions** | **Integer** | Analyzed mentions |  |
| **positive** | **Integer** | Positive and very positive |  |
| **neutral** | **Integer** |  |  |
| **negative** | **Integer** | Negative and very negative |  |
| **positive_pct** | **Float** |  |  |
| **neutral_pct** | **Float** |  |  |
| **negative_pct** | **Float** |  |  |
| **net_score** | **Float** | Positive minus negative, divided by mentions, times 100 |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SentimentBreakdownCounts.new(
  mentions: null,
  positive: null,
  neutral: null,
  negative: null,
  positive_pct: null,
  neutral_pct: null,
  negative_pct: null,
  net_score: null
)
```


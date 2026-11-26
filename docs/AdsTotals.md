# LLMPulse::AdsTotals

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ads** | **Integer** |  |  |
| **advertisers** | **Integer** |  |  |
| **your_ads** | **Integer** |  |  |
| **your_share** | **Float** | your_ads over ads, 0-100 |  |
| **avg_position** | **Float** |  |  |
| **executions_with_ads** | **Integer** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AdsTotals.new(
  ads: null,
  advertisers: null,
  your_ads: null,
  your_share: null,
  avg_position: null,
  executions_with_ads: null
)
```


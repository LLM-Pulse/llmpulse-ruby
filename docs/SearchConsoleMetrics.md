# LLMPulse::SearchConsoleMetrics

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **impressions** | **Integer** |  | [optional] |
| **clicks** | **Integer** |  | [optional] |
| **ctr** | **Float** | 0..1 fraction | [optional] |
| **position** | **Float** | Impression-weighted average position | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleMetrics.new(
  impressions: null,
  clicks: null,
  ctr: null,
  position: null
)
```


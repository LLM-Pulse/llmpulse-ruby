# LLMPulse::AiTrafficResponseTotals

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **users** | **Integer** |  |  |
| **sessions** | **Integer** |  |  |
| **conversions** | **Integer** |  |  |
| **conversion_rate** | **Float** | conversions as a percentage (0-100) of sessions; 0 without sessions |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiTrafficResponseTotals.new(
  users: null,
  sessions: null,
  conversions: null,
  conversion_rate: null
)
```


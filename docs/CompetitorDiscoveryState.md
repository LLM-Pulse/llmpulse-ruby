# LLMPulse::CompetitorDiscoveryState

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** | The last discovery run: pending, processing, completed or failed; null when none ever ran | [optional] |
| **loading** | **Boolean** | A discovery run is in progress |  |
| **generated_at** | **Time** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CompetitorDiscoveryState.new(
  status: null,
  loading: null,
  generated_at: null
)
```


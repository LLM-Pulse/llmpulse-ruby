# LLMPulse::AiOverviewResultCounts

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_responses** | **Integer** | AI Overview runs in the window |  |
| **responses_with_results** | **Integer** | Runs that returned an AI Overview |  |
| **result_rate** | **Float** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiOverviewResultCounts.new(
  total_responses: null,
  responses_with_results: null,
  result_rate: null
)
```


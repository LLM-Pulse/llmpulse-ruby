# LLMPulse::AccountAgentUsage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **percent_used** | **Integer** | Whole percent used, rounded down, from 0 to 100; 100 means the allowance is spent and new questions wait until resets_on. null when unlimited is true | [optional] |
| **unlimited** | **Boolean** |  | [optional] |
| **included** | **Boolean** | Whether the plan includes the in-app AI assistant. false on a plan without it, where percent_used is 100 | [optional] |
| **period** | **String** | Always month | [optional] |
| **resets_on** | **Date** | The first day of next month, when the allowance starts again | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AccountAgentUsage.new(
  percent_used: null,
  unlimited: null,
  included: null,
  period: null,
  resets_on: null
)
```


# LLMPulse::ProjectDraftResponseLimits

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompts_available** | **Integer** | Prompts the account can still add; null when unlimited |  |
| **max_prompts_per_request** | **Integer** |  |  |
| **max_competitors** | **Integer** | Competitors the plan allows per project |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDraftResponseLimits.new(
  prompts_available: null,
  max_prompts_per_request: null,
  max_competitors: null
)
```


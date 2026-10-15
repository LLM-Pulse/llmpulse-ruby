# LLMPulse::UpdateRecommendationItemRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **status** | **String** | completed, archived, or active to restore the item |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UpdateRecommendationItemRequest.new(
  project_id: null,
  status: null
)
```


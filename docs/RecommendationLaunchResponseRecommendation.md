# LLMPulse::RecommendationLaunchResponseRecommendation

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | Poll GET /recommendations/{id} with it |  |
| **recommendation_type** | **String** |  |  |
| **status** | **String** | Always pending |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::RecommendationLaunchResponseRecommendation.new(
  id: null,
  recommendation_type: null,
  status: null,
  created_at: null
)
```


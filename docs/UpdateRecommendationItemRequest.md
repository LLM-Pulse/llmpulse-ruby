# LLMPulse::UpdateRecommendationItemRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **status** | **String** | completed, archived, or active to restore the item |  |
| **reason** | **String** | Optional, with status archived only. competitor only on a PR &amp; Citation Building item that targets a domain. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UpdateRecommendationItemRequest.new(
  project_id: null,
  status: null,
  reason: null
)
```


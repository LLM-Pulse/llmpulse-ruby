# LLMPulse::CompetitorCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **competitor** | [**CompetitorCreateResponseCompetitor**](CompetitorCreateResponseCompetitor.md) |  |  |
| **competitors_remaining** | **Integer** | Competitors the plan still allows in this project; null when unlimited |  |
| **total_competitors** | **Integer** |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CompetitorCreateResponse.new(
  project_id: null,
  competitor: null,
  competitors_remaining: null,
  total_competitors: null,
  request_id: null
)
```


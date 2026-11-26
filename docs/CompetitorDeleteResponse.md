# LLMPulse::CompetitorDeleteResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **deleted** | **Boolean** | Always true |  |
| **id** | **Integer** |  |  |
| **brand_name** | **String** |  |  |
| **domain** | **String** |  |  |
| **total_competitors** | **Integer** | Competitors left in the project |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CompetitorDeleteResponse.new(
  project_id: null,
  deleted: null,
  id: null,
  brand_name: null,
  domain: null,
  total_competitors: null,
  request_id: null
)
```


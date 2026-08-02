# LLMPulse::UpdateCompetitorRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **brand_name** | **String** |  | [optional] |
| **matching_names** | **Array&lt;String&gt;** |  | [optional] |
| **color** | **String** | Hex color, e.g. #1a2b3c | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UpdateCompetitorRequest.new(
  project_id: null,
  brand_name: null,
  matching_names: null,
  color: null
)
```


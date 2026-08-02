# LLMPulse::CreateCompetitorRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **brand_name** | **String** |  |  |
| **domain** | **String** | URL is accepted and normalised to host (e.g. https://www.openai.com → openai.com) |  |
| **matching_names** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateCompetitorRequest.new(
  project_id: null,
  brand_name: null,
  domain: null,
  matching_names: null
)
```


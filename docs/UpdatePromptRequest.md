# LLMPulse::UpdatePromptRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **prompt_type** | **String** | Search intent | [optional] |
| **brand_kind** | **String** | Brand focus: brand (your own brand or products), brand_other (competing brands), non_brand (generic) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UpdatePromptRequest.new(
  project_id: null,
  prompt_type: null,
  brand_kind: null
)
```


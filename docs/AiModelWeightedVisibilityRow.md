# LLMPulse::AiModelWeightedVisibilityRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **model** | **String** | AI model key, as /dimensions/models lists it | [optional] |
| **label** | **String** | Display name of the model | [optional] |
| **color** | **String** | Hex color the app charts the model with | [optional] |
| **weighted_visibility_score** | **Float** | The brand&#39;s AI Visibility Score points in the model; 0 when it has none | [optional] |
| **share_of_total** | **Float** | The model&#39;s percentage (0-100) of total_weighted_visibility_score; null when that total is 0 | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelWeightedVisibilityRow.new(
  model: null,
  label: null,
  color: null,
  weighted_visibility_score: null,
  share_of_total: null
)
```


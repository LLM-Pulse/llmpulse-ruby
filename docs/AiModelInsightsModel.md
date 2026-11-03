# LLMPulse::AiModelInsightsModel

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **model** | **String** | AI model key, as /dimensions/models lists it | [optional] |
| **label** | **String** | Display name of the model | [optional] |
| **color** | **String** | Hex color the app charts the model with | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelInsightsModel.new(
  model: null,
  label: null,
  color: null
)
```


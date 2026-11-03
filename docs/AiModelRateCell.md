# LLMPulse::AiModelRateCell

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **value** | **Float** | numerator as a percentage (0-100) of denominator; null when the model has no answers in the window | [optional] |
| **numerator** | **Integer** | Mentions of the actor (or answers citing it) in the model&#39;s answers | [optional] |
| **denominator** | **Integer** | Answers of the model in the window | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelRateCell.new(
  value: null,
  numerator: null,
  denominator: null
)
```


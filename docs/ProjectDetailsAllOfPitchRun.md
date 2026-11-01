# LLMPulse::ProjectDetailsAllOfPitchRun

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** | starting before the run begins, running while answers arrive, ready once every AI model has answered or stopped trying | [optional] |
| **launched_at** | **Time** |  | [optional] |
| **settled_at** | **Time** |  | [optional] |
| **models** | **Array&lt;String&gt;** | The AI models the run asks, fixed when it starts | [optional] |
| **answers_expected** | **Integer** |  | [optional] |
| **answers_received** | **Integer** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetailsAllOfPitchRun.new(
  status: null,
  launched_at: null,
  settled_at: null,
  models: null,
  answers_expected: null,
  answers_received: null
)
```


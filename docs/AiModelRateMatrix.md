# LLMPulse::AiModelRateMatrix

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **denominators_by_model** | **Hash&lt;String, Integer&gt;** | Answers of each model in the window, keyed by model | [optional] |
| **actors** | [**Array&lt;AiModelRateMatrixActor&gt;**](AiModelRateMatrixActor.md) | The project and each competitor with a mention (or citation) in the window (only the competitors given in competitors, when it is given), by total descending | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelRateMatrix.new(
  denominators_by_model: null,
  actors: null
)
```


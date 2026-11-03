# LLMPulse::AiModelRateMatrixActor

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** |  | [optional] |
| **id** | **Integer** | Project id, or competitor id | [optional] |
| **competitor_id** | **Integer** | Null for the project, the competitor id otherwise | [optional] |
| **name** | **String** |  | [optional] |
| **domain** | **String** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional] |
| **total** | **Integer** | The actor&#39;s numerators summed over the models | [optional] |
| **models** | [**Hash&lt;String, AiModelRateCell&gt;**](AiModelRateCell.md) | One cell per model, keyed by model | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelRateMatrixActor.new(
  type: null,
  id: null,
  competitor_id: null,
  name: null,
  domain: null,
  total: null,
  models: null
)
```


# LLMPulse::AiModelWeightedVisibilityMatrixActor

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** |  | [optional] |
| **id** | **Integer** | Project id, or competitor id | [optional] |
| **competitor_id** | **Integer** | Null for the project, the competitor id otherwise | [optional] |
| **name** | **String** |  | [optional] |
| **domain** | **String** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional] |
| **total_weighted_visibility_score** | **Float** | The actor&#39;s AI Visibility Score points summed over the models | [optional] |
| **models** | [**Hash&lt;String, AiModelWeightedVisibilityCell&gt;**](AiModelWeightedVisibilityCell.md) | One cell per model, keyed by model | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelWeightedVisibilityMatrixActor.new(
  type: null,
  id: null,
  competitor_id: null,
  name: null,
  domain: null,
  total_weighted_visibility_score: null,
  models: null
)
```


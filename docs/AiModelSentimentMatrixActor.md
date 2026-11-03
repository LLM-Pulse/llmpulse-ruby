# LLMPulse::AiModelSentimentMatrixActor

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** |  | [optional] |
| **id** | **Integer** | Project id, or competitor id | [optional] |
| **competitor_id** | **Integer** | Null for the project, the competitor id otherwise | [optional] |
| **name** | **String** |  | [optional] |
| **domain** | **String** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional] |
| **total_sentiments** | **Integer** | The actor&#39;s sentiment verdicts summed over the models | [optional] |
| **models** | [**Hash&lt;String, AiModelSentimentCell&gt;**](AiModelSentimentCell.md) | One cell per model, keyed by model | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelSentimentMatrixActor.new(
  type: null,
  id: null,
  competitor_id: null,
  name: null,
  domain: null,
  total_sentiments: null,
  models: null
)
```


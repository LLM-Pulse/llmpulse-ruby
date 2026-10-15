# LLMPulse::OwnedMediaCitingAnswer

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **answer_id** | **Integer** | The answer (prompt execution) id, readable with GET /answers/{id} | [optional] |
| **prompt_id** | **Integer** |  | [optional] |
| **prompt_text** | **String** |  | [optional] |
| **model** | **String** |  | [optional] |
| **country_code** | **String** |  | [optional] |
| **language_code** | **String** |  | [optional] |
| **executed_at** | **Time** |  | [optional] |
| **excerpt** | **String** | The start of the answer as plain text (at most 300 characters) | [optional] |
| **app_url** | **String** | The answer in the app | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaCitingAnswer.new(
  answer_id: null,
  prompt_id: null,
  prompt_text: null,
  model: null,
  country_code: null,
  language_code: null,
  executed_at: null,
  excerpt: null,
  app_url: null
)
```


# LLMPulse::AiModelDeclinedAnswersResponseByPrompt

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** | Prompts with an answer in the window | [optional] |
| **data** | [**Array&lt;AiModelDeclinedAnswersResponseByPromptDataInner&gt;**](AiModelDeclinedAnswersResponseByPromptDataInner.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelDeclinedAnswersResponseByPrompt.new(
  page: null,
  per_page: null,
  total: null,
  data: null
)
```


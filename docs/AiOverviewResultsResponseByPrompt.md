# LLMPulse::AiOverviewResultsResponseByPrompt

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Prompts with an AI Overview run in the window |  |
| **data** | [**Array&lt;AiOverviewResultsResponseByPromptDataInner&gt;**](AiOverviewResultsResponseByPromptDataInner.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiOverviewResultsResponseByPrompt.new(
  page: null,
  per_page: null,
  total: null,
  data: null
)
```


# LLMPulse::SuggestedPromptsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** |  |  |
| **data** | [**Array&lt;SuggestedPrompt&gt;**](SuggestedPrompt.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SuggestedPromptsResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  data: null,
  request_id: null
)
```


# LLMPulse::PromptDeleteResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **deleted** | **Boolean** | Always true |  |
| **id** | **Integer** |  |  |
| **raw_input** | **String** |  |  |
| **total_after** | **Integer** | Prompts left in the project |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptDeleteResponse.new(
  project_id: null,
  deleted: null,
  id: null,
  raw_input: null,
  total_after: null,
  request_id: null
)
```


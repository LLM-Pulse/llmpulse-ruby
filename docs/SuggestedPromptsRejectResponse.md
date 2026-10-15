# LLMPulse::SuggestedPromptsRejectResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **rejected** | **Integer** |  |  |
| **ids** | **Array&lt;Integer&gt;** | The suggestions that were pending and are now rejected |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SuggestedPromptsRejectResponse.new(
  project_id: null,
  rejected: null,
  ids: null,
  request_id: null
)
```


# LLMPulse::ProjectDraftResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft** | [**ProjectDraftRecord**](ProjectDraftRecord.md) |  |  |
| **suggestions** | [**ProjectDraftSuggestions**](ProjectDraftSuggestions.md) |  |  |
| **limits** | [**ProjectDraftResponseLimits**](ProjectDraftResponseLimits.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDraftResponse.new(
  draft: null,
  suggestions: null,
  limits: null,
  request_id: null
)
```


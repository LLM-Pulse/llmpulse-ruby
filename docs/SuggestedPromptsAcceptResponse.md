# LLMPulse::SuggestedPromptsAcceptResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **accepted** | [**Array&lt;SuggestedPromptsAcceptResponseAcceptedInner&gt;**](SuggestedPromptsAcceptResponseAcceptedInner.md) |  |  |
| **skipped** | [**Array&lt;CatalogPromptSuggestionsAcceptResponseSkippedInner&gt;**](CatalogPromptSuggestionsAcceptResponseSkippedInner.md) |  |  |
| **prompts_available** | **Integer** | Prompt slots left on the plan; null when unlimited |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SuggestedPromptsAcceptResponse.new(
  project_id: null,
  accepted: null,
  skipped: null,
  prompts_available: null,
  request_id: null
)
```


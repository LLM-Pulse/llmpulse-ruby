# LLMPulse::CatalogPromptSuggestionsAcceptResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **accepted** | [**Array&lt;CatalogPromptSuggestionsAcceptResponseAcceptedInner&gt;**](CatalogPromptSuggestionsAcceptResponseAcceptedInner.md) |  |  |
| **skipped** | [**Array&lt;CatalogPromptSuggestionsAcceptResponseSkippedInner&gt;**](CatalogPromptSuggestionsAcceptResponseSkippedInner.md) |  |  |
| **prompts_available** | **Integer** | Prompt slots left on the plan; null when unlimited |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CatalogPromptSuggestionsAcceptResponse.new(
  project_id: null,
  accepted: null,
  skipped: null,
  prompts_available: null,
  request_id: null
)
```


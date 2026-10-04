# LLMPulse::CatalogPromptSuggestionsAcceptResponseSkippedInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **suggestion_id** | **Integer** |  |  |
| **reason** | **String** | accepted or rejected (the suggestion was no longer pending), or pending_deletion |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CatalogPromptSuggestionsAcceptResponseSkippedInner.new(
  suggestion_id: null,
  reason: null
)
```


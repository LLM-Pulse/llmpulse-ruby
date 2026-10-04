# LLMPulse::CatalogPromptSuggestionsAcceptResponseAcceptedInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **suggestion_id** | **Integer** |  |  |
| **prompt_id** | **Integer** |  |  |
| **collection_id** | **Integer** | The collection named after the product; null when the product has no title or the team member cannot create tags |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CatalogPromptSuggestionsAcceptResponseAcceptedInner.new(
  suggestion_id: null,
  prompt_id: null,
  collection_id: null
)
```


# LLMPulse::CatalogPromptSuggestionsCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **created** | **Integer** |  |  |
| **skipped** | **Integer** | Generated prompts not saved because the project already holds them as a suggestion (from any source or product, in any status). |  |
| **data** | [**Array&lt;CatalogPromptSuggestion&gt;**](CatalogPromptSuggestion.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CatalogPromptSuggestionsCreateResponse.new(
  project_id: null,
  created: null,
  skipped: null,
  data: null,
  request_id: null
)
```


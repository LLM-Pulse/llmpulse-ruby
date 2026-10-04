# LLMPulse::CatalogPromptSuggestionsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** |  |  |
| **data** | [**Array&lt;CatalogPromptSuggestion&gt;**](CatalogPromptSuggestion.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CatalogPromptSuggestionsResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  data: null,
  request_id: null
)
```


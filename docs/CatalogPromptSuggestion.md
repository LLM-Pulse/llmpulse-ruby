# LLMPulse::CatalogPromptSuggestion

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **prompt** | **String** |  |  |
| **status** | **String** | pending, accepted or rejected |  |
| **source** | **String** | Always catalog |  |
| **country_code** | **String** |  |  |
| **language_code** | **String** |  |  |
| **product** | [**CatalogPromptSuggestionProduct**](CatalogPromptSuggestionProduct.md) |  |  |
| **prompt_id** | **Integer** | The tracked prompt an accepted suggestion became; null until accepted |  |
| **accepted_at** | **Time** | When the suggestion was accepted; null until then |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CatalogPromptSuggestion.new(
  id: null,
  prompt: null,
  status: null,
  source: null,
  country_code: null,
  language_code: null,
  product: null,
  prompt_id: null,
  accepted_at: null,
  created_at: null
)
```


# LLMPulse::AiModelCitationsRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **model** | **String** | AI model key, as /dimensions/models lists it | [optional] |
| **label** | **String** | Display name of the model | [optional] |
| **color** | **String** | Hex color the app charts the model with | [optional] |
| **citations_count** | **Integer** | Citations of the brand&#39;s URLs in the model&#39;s answers; 0 when it has none | [optional] |
| **share_of_total** | **Float** | The model&#39;s percentage (0-100) of total_citations; null when total_citations is 0 | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelCitationsRow.new(
  model: null,
  label: null,
  color: null,
  citations_count: null,
  share_of_total: null
)
```


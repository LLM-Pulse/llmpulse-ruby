# LLMPulse::AiModelMentionsRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **model** | **String** | AI model key, as /dimensions/models lists it | [optional] |
| **label** | **String** | Display name of the model | [optional] |
| **color** | **String** | Hex color the app charts the model with | [optional] |
| **mentions_count** | **Integer** | Brand mentions in the model&#39;s answers; 0 when it has none | [optional] |
| **share_of_total** | **Float** | The model&#39;s percentage (0-100) of total_mentions; null when total_mentions is 0 | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelMentionsRow.new(
  model: null,
  label: null,
  color: null,
  mentions_count: null,
  share_of_total: null
)
```


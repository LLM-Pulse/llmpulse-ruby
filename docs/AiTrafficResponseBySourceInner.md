# LLMPulse::AiTrafficResponseBySourceInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **source** | **String** | AI source slug, such as chatgpt or perplexity |  |
| **name** | **String** | Display name of the source |  |
| **users** | **Integer** |  |  |
| **sessions** | **Integer** |  |  |
| **conversions** | **Integer** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiTrafficResponseBySourceInner.new(
  source: null,
  name: null,
  users: null,
  sessions: null,
  conversions: null
)
```


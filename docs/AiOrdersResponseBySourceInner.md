# LLMPulse::AiOrdersResponseBySourceInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **source** | **String** | AI assistant slug, e.g. chatgpt or perplexity |  |
| **name** | **String** | Display name, e.g. ChatGPT |  |
| **orders** | **Integer** |  |  |
| **revenue** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiOrdersResponseBySourceInner.new(
  source: null,
  name: null,
  orders: null,
  revenue: null
)
```


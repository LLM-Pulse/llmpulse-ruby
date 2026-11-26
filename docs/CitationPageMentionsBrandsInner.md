# LLMPulse::CitationPageMentionsBrandsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **actor_type** | **String** | project or competitor |  |
| **competitor_id** | **Integer** | Null for the project |  |
| **name** | **String** |  |  |
| **domain** | **String** | The competitor&#39;s domain, or the project&#39;s URL (null when it has none) |  |
| **position** | **Integer** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationPageMentionsBrandsInner.new(
  actor_type: null,
  competitor_id: null,
  name: null,
  domain: null,
  position: null
)
```


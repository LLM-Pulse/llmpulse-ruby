# LLMPulse::CitationPageMentionsMentionsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **matched_key** | **String** | The name that matched |  |
| **snippet** | **String** |  |  |
| **start_offset** | **Integer** |  |  |
| **end_offset** | **Integer** |  |  |
| **position** | **Integer** |  |  |
| **actor_type** | **String** | project or competitor |  |
| **competitor_id** | **Integer** | Null for the project |  |
| **actor_name** | **String** |  |  |
| **actor_domain** | **String** | The competitor&#39;s domain, or the project&#39;s URL |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationPageMentionsMentionsInner.new(
  id: null,
  matched_key: null,
  snippet: null,
  start_offset: null,
  end_offset: null,
  position: null,
  actor_type: null,
  competitor_id: null,
  actor_name: null,
  actor_domain: null
)
```


# LLMPulse::UrlListWithStats

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **name** | **String** |  |  |
| **description** | **String** |  |  |
| **currency** | **String** | The currency of the entry costs. |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **entries_count** | **Integer** |  |  |
| **cited_entries** | **Integer** | Entries an AI answer cited in the window. |  |
| **citations** | **Integer** | AI answers citing any entry in the window, each once. |  |
| **last_cited_at** | **Time** | The latest answer citing an entry, up to the window&#39;s end. |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListWithStats.new(
  id: null,
  name: null,
  description: null,
  currency: null,
  created_at: null,
  updated_at: null,
  entries_count: null,
  cited_entries: null,
  citations: null,
  last_cited_at: null
)
```


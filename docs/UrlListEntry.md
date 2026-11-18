# LLMPulse::UrlListEntry

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **value** | **String** | The exact URL, \&quot;host/path\&quot; of a prefix, or the host of a domain rule. |  |
| **match_type** | **String** |  |  |
| **host** | **String** |  |  |
| **status** | **String** |  |  |
| **added_on** | **Date** |  |  |
| **cost** | **Float** |  |  |
| **channel** | **String** |  |  |
| **citations** | **Integer** |  |  |
| **cited_pages** | **Integer** |  |  |
| **first_cited_at** | **Time** |  |  |
| **last_cited_at** | **Time** |  |  |
| **days_to_first_citation** | **Integer** |  |  |
| **avg_citation_position** | **Float** |  |  |
| **models** | **Array&lt;String&gt;** |  |  |
| **brand_mentioned** | **Boolean** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListEntry.new(
  id: null,
  value: null,
  match_type: null,
  host: null,
  status: null,
  added_on: null,
  cost: null,
  channel: null,
  citations: null,
  cited_pages: null,
  first_cited_at: null,
  last_cited_at: null,
  days_to_first_citation: null,
  avg_citation_position: null,
  models: null,
  brand_mentioned: null
)
```


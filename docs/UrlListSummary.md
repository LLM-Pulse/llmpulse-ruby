# LLMPulse::UrlListSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **entries_count** | **Integer** |  |  |
| **cited_entries** | **Integer** |  |  |
| **citations** | **Integer** | AI answers citing any entry in the window, each once. |  |
| **answers** | **Integer** | AI answers in the window, the citation rate&#39;s denominator. |  |
| **citation_rate** | **Float** | citations over answers, in percent. |  |
| **avg_citation_position** | **Float** |  |  |
| **median_days_to_first_citation** | **Integer** |  |  |
| **total_cost** | **Float** |  |  |
| **cost_per_cited_entry** | **Float** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListSummary.new(
  entries_count: null,
  cited_entries: null,
  citations: null,
  answers: null,
  citation_rate: null,
  avg_citation_position: null,
  median_days_to_first_citation: null,
  total_cost: null,
  cost_per_cited_entry: null
)
```


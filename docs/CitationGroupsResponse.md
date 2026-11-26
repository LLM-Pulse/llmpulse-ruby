# LLMPulse::CitationGroupsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **view** | **String** | url, domain or host |  |
| **filters** | [**CitationIntelligenceFiltersEcho**](CitationIntelligenceFiltersEcho.md) |  |  |
| **data** | [**Array&lt;CitationGroupRow&gt;**](CitationGroupRow.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationGroupsResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  view: null,
  filters: null,
  data: null
)
```


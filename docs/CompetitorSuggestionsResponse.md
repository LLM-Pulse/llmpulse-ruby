# LLMPulse::CompetitorSuggestionsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **basis** | **String** |  |  |
| **discovery** | [**CompetitorDiscoveryState**](CompetitorDiscoveryState.md) |  |  |
| **data** | [**Array&lt;CompetitorSuggestion&gt;**](CompetitorSuggestion.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CompetitorSuggestionsResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  basis: null,
  discovery: null,
  data: null
)
```


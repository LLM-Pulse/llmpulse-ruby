# LLMPulse::CompetitorCreateResponseCompetitor

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **brand_name** | **String** |  |  |
| **domain** | **String** |  |  |
| **citation_match_mode** | [**CitationMatchMode**](CitationMatchMode.md) |  |  |
| **citation_match_path** | **String** | Set only when citation_match_mode is path_prefix |  |
| **color** | **String** |  |  |
| **matching_names** | **Array&lt;String&gt;** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CompetitorCreateResponseCompetitor.new(
  id: null,
  brand_name: null,
  domain: null,
  citation_match_mode: null,
  citation_match_path: null,
  color: null,
  matching_names: null
)
```


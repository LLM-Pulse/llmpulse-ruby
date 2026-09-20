# LLMPulse::UpdateCompetitorRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **brand_name** | **String** |  | [optional] |
| **domain** | **String** | Website domain or host used for citation matching. A full URL is accepted and normalised to its host. | [optional] |
| **matching_names** | **Array&lt;String&gt;** |  | [optional] |
| **color** | **String** | Hex color, e.g. #1a2b3c | [optional] |
| **citation_match_mode** | **String** |  | [optional] |
| **citation_match_path** | **String** | Required when changing citation_match_mode to path_prefix | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UpdateCompetitorRequest.new(
  project_id: null,
  brand_name: null,
  domain: null,
  matching_names: null,
  color: null,
  citation_match_mode: null,
  citation_match_path: null
)
```


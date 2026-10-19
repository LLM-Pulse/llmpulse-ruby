# LLMPulse::UpdateCompetitorRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **brand_name** | **String** |  | [optional] |
| **domain** | **String** | Website domain or host used for citation matching. A full URL is accepted and normalised to its host. | [optional] |
| **matching_names** | **Array&lt;String&gt;** | FULL replacement list of the names this competitor is matched by; brand_name is added automatically. At most 50 names in all, brand_name included, of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) and nothing in the request is applied | [optional] |
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


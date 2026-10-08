# LLMPulse::Competitor

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **name** | **String** |  | [optional] |
| **domain** | **String** | Bare (scheme-less) domain. Null only on the own-brand row (include_project_brand&#x3D;true) when the project has no URL. | [optional] |
| **matching_names** | **Array&lt;String&gt;** | Alternative names matched as this competitor. Absent on the own-brand row | [optional] |
| **citation_match_mode** | [**CitationMatchMode**](CitationMatchMode.md) |  | [optional] |
| **citation_match_path** | **String** | Set only when citation_match_mode is path_prefix | [optional] |
| **actor_type** | **String** | Only present when include_project_brand&#x3D;true | [optional] |
| **is_own** | **Boolean** | Only present when include_project_brand&#x3D;true | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::Competitor.new(
  id: null,
  name: null,
  domain: null,
  matching_names: null,
  citation_match_mode: null,
  citation_match_path: null,
  actor_type: null,
  is_own: null
)
```


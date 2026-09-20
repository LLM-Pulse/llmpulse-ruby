# LLMPulse::CreateCompetitorRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **brand_name** | **String** |  |  |
| **domain** | **String** | URL is accepted and normalised to host (e.g. https://www.openai.com → openai.com) |  |
| **matching_names** | **Array&lt;String&gt;** |  | [optional] |
| **citation_match_mode** | **String** | domain includes the registrable domain and all subdomains; host requires the exact hostname; path_prefix also requires citation_match_path | [optional][default to &#39;domain&#39;] |
| **citation_match_path** | **String** | Required when citation_match_mode&#x3D;path_prefix, e.g. /es. Case-sensitive; trailing slash is optional; query and fragment are ignored | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateCompetitorRequest.new(
  project_id: null,
  brand_name: null,
  domain: null,
  matching_names: null,
  citation_match_mode: null,
  citation_match_path: null
)
```


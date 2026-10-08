# LLMPulse::ProjectDetailsAllOfStats

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompts_count** | **Integer** |  | [optional] |
| **prompts_by_brand_kind** | [**ProjectDetailsAllOfStatsPromptsByBrandKind**](ProjectDetailsAllOfStatsPromptsByBrandKind.md) |  | [optional] |
| **competitors_count** | **Integer** |  | [optional] |
| **collections_count** | **Integer** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetailsAllOfStats.new(
  prompts_count: null,
  prompts_by_brand_kind: null,
  competitors_count: null,
  collections_count: null
)
```


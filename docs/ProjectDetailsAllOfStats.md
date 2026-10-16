# LLMPulse::ProjectDetailsAllOfStats

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompts_count** | **Integer** | Active prompts in the project | [optional] |
| **prompts_available** | **Integer** | Prompts that can still be added to this project, the lower of its free slots under prompt_limit and the prompts left in the account quota; null when neither caps it | [optional] |
| **prompts_by_brand_kind** | [**ProjectDetailsAllOfStatsPromptsByBrandKind**](ProjectDetailsAllOfStatsPromptsByBrandKind.md) |  | [optional] |
| **competitors_count** | **Integer** |  | [optional] |
| **collections_count** | **Integer** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetailsAllOfStats.new(
  prompts_count: null,
  prompts_available: null,
  prompts_by_brand_kind: null,
  competitors_count: null,
  collections_count: null
)
```


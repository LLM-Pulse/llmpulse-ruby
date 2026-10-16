# LLMPulse::ProjectDetailsAllOfStats

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompts_count** | **Integer** |  | [optional] |
| **prompts_by_brand_kind** | [**ProjectDetailsAllOfStatsPromptsByBrandKind**](ProjectDetailsAllOfStatsPromptsByBrandKind.md) |  | [optional] |
| **competitors_count** | **Integer** |  | [optional] |
| **collections_count** | **Integer** |  | [optional] |
| **prompts_available** | **Integer** | How many prompts can still be added to this project now, the same number the Prompts page offers. The lower of the project&#39;s free slots under prompt_limit and the account&#39;s remaining prompts; 0 when either is full (a project over its limit keeps its prompts). Null when neither caps it | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetailsAllOfStats.new(
  prompts_count: null,
  prompts_by_brand_kind: null,
  competitors_count: null,
  collections_count: null,
  prompts_available: null
)
```


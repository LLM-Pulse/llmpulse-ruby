# LLMPulse::PromptCategorization

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **raw_input** | **String** |  |  |
| **prompt_type** | **String** |  | [optional] |
| **brand_kind** | **String** |  | [optional] |
| **categorization_source** | **String** | manual after an edit by hand; the prompt page&#39;s revert hands it back to automatic categorization | [optional] |
| **manually_categorized** | **Boolean** |  |  |
| **categorized_at** | **Time** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptCategorization.new(
  id: null,
  raw_input: null,
  prompt_type: null,
  brand_kind: null,
  categorization_source: null,
  manually_categorized: null,
  categorized_at: null
)
```


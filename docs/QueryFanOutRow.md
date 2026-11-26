# LLMPulse::QueryFanOutRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **query_text** | **String** | The sub-query a model issued (view&#x3D;query) | [optional] |
| **count** | **Integer** | Times it was issued (view&#x3D;query) | [optional] |
| **share** | **Float** | Share of all sub-query occurrences, on a 0-100 scale (view&#x3D;query) | [optional] |
| **prompt_id** | **Integer** | view&#x3D;prompt | [optional] |
| **prompt_text** | **String** | view&#x3D;prompt | [optional] |
| **variations_count** | **Integer** | Distinct sub-queries issued for the prompt (view&#x3D;prompt) | [optional] |
| **total_count** | **Integer** | Sub-queries issued for the prompt, repeats included (view&#x3D;prompt) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::QueryFanOutRow.new(
  query_text: null,
  count: null,
  share: null,
  prompt_id: null,
  prompt_text: null,
  variations_count: null,
  total_count: null
)
```


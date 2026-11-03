# LLMPulse::AiModelInsightsFiltersEcho

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **granularity** | **String** | day, week or month; day when not given | [optional] |
| **country_code** | **String** | Comma-separated country codes | [optional] |
| **language_code** | **String** | Comma-separated language codes | [optional] |
| **collection_id** | **String** | Comma-separated collection ids | [optional] |
| **prompt_type** | **String** | Comma-separated prompt types | [optional] |
| **brand_kind** | **String** |  | [optional] |
| **competitors** | **Array&lt;Integer&gt;** | Competitor ids from the competitors parameter; empty when it was not given | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelInsightsFiltersEcho.new(
  from: null,
  to: null,
  granularity: null,
  country_code: null,
  language_code: null,
  collection_id: null,
  prompt_type: null,
  brand_kind: null,
  competitors: null
)
```


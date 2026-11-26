# LLMPulse::AiModelInsightsReportFiltersEcho

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **from** | **Time** |  |  |
| **to** | **Time** |  |  |
| **granularity** | **String** |  |  |
| **country_code** | **String** | Comma-separated country codes | [optional] |
| **language_code** | **String** | Comma-separated language codes | [optional] |
| **collection_id** | **String** | Comma-separated collection ids | [optional] |
| **prompt_type** | **String** | Comma-separated prompt types | [optional] |
| **brand_kind** | **String** |  | [optional] |
| **model** | **String** | The model filter; always ai_overview on the AI Overview report | [optional] |
| **competitors** | **Array&lt;Integer&gt;** | Competitor ids from the competitors parameter; empty when it was not given |  |
| **brand1** | **String** | Position distribution only. The id, as a string, of the competitor compared as the first brand; left out for the project brand | [optional] |
| **brand2** | **String** | Position distribution only. The id, as a string, of the competitor compared as the second brand, by default the competitor with the most mentions; left out when the project has none to compare | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelInsightsReportFiltersEcho.new(
  from: null,
  to: null,
  granularity: null,
  country_code: null,
  language_code: null,
  collection_id: null,
  prompt_type: null,
  brand_kind: null,
  model: null,
  competitors: null,
  brand1: null,
  brand2: null
)
```


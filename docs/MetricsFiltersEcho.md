# LLMPulse::MetricsFiltersEcho

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **metrics** | **Array&lt;String&gt;** | Requested metrics after alias resolution (mention_rate is echoed as visibility) | [optional] |
| **granularity** | **String** | day, week or month | [optional] |
| **model** | **String** | The model filter, or null when absent or not enabled for the account | [optional] |
| **collection_id** | **String** | The collection_id parameter as sent (one id or a comma-separated list) | [optional] |
| **collection_ids** | **Array&lt;Integer&gt;** |  | [optional] |
| **domains** | **Array&lt;String&gt;** |  | [optional] |
| **country_code** | **String** | Comma-separated country codes | [optional] |
| **language_code** | **String** | Comma-separated language codes | [optional] |
| **prompt** | **Integer** | The prompt id filter | [optional] |
| **prompt_type** | **String** | Comma-separated prompt types | [optional] |
| **brand_kind** | **String** |  | [optional] |
| **competitors** | **Array&lt;Integer&gt;** | Competitor ids from the competitors parameter; empty when it was not given | [optional] |
| **include_project** | **Boolean** |  | [optional] |
| **query** | **String** | Only present when a query filter was given | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::MetricsFiltersEcho.new(
  metrics: null,
  granularity: null,
  model: null,
  collection_id: null,
  collection_ids: null,
  domains: null,
  country_code: null,
  language_code: null,
  prompt: null,
  prompt_type: null,
  brand_kind: null,
  competitors: null,
  include_project: null,
  query: null
)
```


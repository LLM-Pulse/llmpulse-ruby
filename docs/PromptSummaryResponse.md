# LLMPulse::PromptSummaryResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **filters** | [**MetricsFiltersEcho**](MetricsFiltersEcho.md) |  | [optional] |
| **breakdown** | **String** |  | [optional] |
| **sort** | **String** |  | [optional] |
| **sort_dir** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **data** | [**Array&lt;PromptSummaryRow&gt;**](PromptSummaryRow.md) |  | [optional] |
| **plan_required_fields** | **Array&lt;String&gt;** | The row fields left out because they need a higher plan (the sentiment fields below Growth); empty when none is |  |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptSummaryResponse.new(
  project_id: null,
  from: null,
  to: null,
  filters: null,
  breakdown: null,
  sort: null,
  sort_dir: null,
  page: null,
  per_page: null,
  total: null,
  data: null,
  plan_required_fields: null,
  request_id: null
)
```


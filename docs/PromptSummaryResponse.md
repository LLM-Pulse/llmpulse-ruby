# LLMPulse::PromptSummaryResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **filters** | **Object** |  | [optional] |
| **breakdown** | **String** |  | [optional] |
| **sort** | **String** |  | [optional] |
| **sort_dir** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **data** | [**Array&lt;PromptSummaryRow&gt;**](PromptSummaryRow.md) |  | [optional] |
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
  request_id: null
)
```


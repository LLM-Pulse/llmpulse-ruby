# LLMPulse::SentimentTopicsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **from** | **Time** |  |  |
| **to** | **Time** |  |  |
| **brand** | [**SentimentBreakdownBrand**](SentimentBreakdownBrand.md) |  |  |
| **sort** | **String** |  |  |
| **sort_dir** | **String** |  |  |
| **data** | [**Array&lt;SentimentTopicRow&gt;**](SentimentTopicRow.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SentimentTopicsResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  from: null,
  to: null,
  brand: null,
  sort: null,
  sort_dir: null,
  data: null
)
```


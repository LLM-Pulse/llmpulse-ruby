# LLMPulse::SentimentsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **data** | [**Array&lt;SentimentRecord&gt;**](SentimentRecord.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SentimentsResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  data: null
)
```


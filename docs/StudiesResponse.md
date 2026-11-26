# LLMPulse::StudiesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Studies matching the filters across every page |  |
| **data** | [**Array&lt;StudySummary&gt;**](StudySummary.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::StudiesResponse.new(
  page: null,
  per_page: null,
  total: null,
  data: null,
  request_id: null
)
```


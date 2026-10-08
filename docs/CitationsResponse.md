# LLMPulse::CitationsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **data** | [**Array&lt;CitationRecord&gt;**](CitationRecord.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationsResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  data: null
)
```


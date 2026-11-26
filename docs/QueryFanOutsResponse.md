# LLMPulse::QueryFanOutsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **view** | **String** | query or prompt, the row shape of data |  |
| **total_occurrences** | **Integer** | Sub-query occurrences across every page (view&#x3D;query) | [optional] |
| **data** | [**Array&lt;QueryFanOutRow&gt;**](QueryFanOutRow.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::QueryFanOutsResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  view: null,
  total_occurrences: null,
  data: null
)
```


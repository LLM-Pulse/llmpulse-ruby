# LLMPulse::ShoppingResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **view** | **String** | products or merchants |  |
| **totals** | [**ShoppingTotals**](ShoppingTotals.md) |  |  |
| **data** | [**Array&lt;ShoppingRow&gt;**](ShoppingRow.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ShoppingResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  view: null,
  totals: null,
  data: null
)
```


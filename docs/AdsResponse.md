# LLMPulse::AdsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **view** | **String** | advertisers or ads |  |
| **totals** | [**AdsTotals**](AdsTotals.md) |  |  |
| **data** | [**Array&lt;AdRow&gt;**](AdRow.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AdsResponse.new(
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


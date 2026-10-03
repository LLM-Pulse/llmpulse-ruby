# LLMPulse::LocalBusinessesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **totals** | [**LocalBusinessesTotals**](LocalBusinessesTotals.md) |  | [optional] |
| **data** | [**Array&lt;LocalBusiness&gt;**](LocalBusiness.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::LocalBusinessesResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  totals: null,
  data: null,
  request_id: null
)
```


# LLMPulse::UrlListsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **filters** | [**UrlListFilters**](UrlListFilters.md) |  |  |
| **total** | **Integer** |  |  |
| **data** | [**Array&lt;UrlListWithStats&gt;**](UrlListWithStats.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListsResponse.new(
  project_id: null,
  filters: null,
  total: null,
  data: null,
  request_id: null
)
```


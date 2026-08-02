# LLMPulse::TopSourcesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **sort** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **data** | [**Array&lt;TopSourcesResponseDataInner&gt;**](TopSourcesResponseDataInner.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TopSourcesResponse.new(
  project_id: null,
  from: null,
  to: null,
  sort: null,
  page: null,
  per_page: null,
  total: null,
  data: null
)
```


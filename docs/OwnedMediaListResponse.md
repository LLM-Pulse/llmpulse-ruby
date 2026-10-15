# LLMPulse::OwnedMediaListResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **provider** | **String** |  | [optional] |
| **view** | **String** |  | [optional] |
| **store** | **String** | provider&#x3D;mobile_apps only | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **data** | [**Array&lt;OwnedMediaRow&gt;**](OwnedMediaRow.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaListResponse.new(
  project_id: null,
  provider: null,
  view: null,
  store: null,
  from: null,
  to: null,
  page: null,
  per_page: null,
  total: null,
  data: null,
  request_id: null
)
```


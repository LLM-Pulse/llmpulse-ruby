# LLMPulse::ListWebhooks200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **data** | [**Array&lt;ListWebhooks200ResponseDataInner&gt;**](ListWebhooks200ResponseDataInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ListWebhooks200Response.new(
  page: null,
  per_page: null,
  total: null,
  data: null,
  request_id: null
)
```


# LLMPulse::CmsContentItemResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **site** | [**CmsSite**](CmsSite.md) |  | [optional] |
| **data** | [**CmsContentItem**](CmsContentItem.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CmsContentItemResponse.new(
  project_id: null,
  site: null,
  data: null,
  request_id: null
)
```


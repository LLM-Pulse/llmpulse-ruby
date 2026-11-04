# LLMPulse::CmsSendResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **created** | **Boolean** | false when this version had already been sent and the existing publication is returned | [optional] |
| **publication** | [**CmsPublication**](CmsPublication.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CmsSendResponse.new(
  project_id: null,
  created: null,
  publication: null,
  request_id: null
)
```


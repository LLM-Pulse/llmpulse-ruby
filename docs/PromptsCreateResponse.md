# LLMPulse::PromptsCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **created** | **Integer** |  | [optional] |
| **skipped** | **Integer** |  | [optional] |
| **total_after** | **Integer** |  | [optional] |
| **prompts_available** | **Integer** |  | [optional] |
| **data** | [**Array&lt;PromptsCreateResponseDataInner&gt;**](PromptsCreateResponseDataInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptsCreateResponse.new(
  project_id: null,
  created: null,
  skipped: null,
  total_after: null,
  prompts_available: null,
  data: null,
  request_id: null
)
```


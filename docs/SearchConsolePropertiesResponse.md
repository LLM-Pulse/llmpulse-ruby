# LLMPulse::SearchConsolePropertiesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **max_properties** | **Integer** | How many properties a project can connect | [optional] |
| **data** | [**Array&lt;SearchConsolePropertiesResponseDataInner&gt;**](SearchConsolePropertiesResponseDataInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsolePropertiesResponse.new(
  project_id: null,
  max_properties: null,
  data: null,
  request_id: null
)
```


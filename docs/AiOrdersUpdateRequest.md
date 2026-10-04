# LLMPulse::AiOrdersUpdateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **platform** | **String** |  |  |
| **currency** | **String** | ISO 4217 code, e.g. EUR |  |
| **from** | **Date** | First day of the window this push replaces |  |
| **to** | **Date** | Last day of the window; at most 400 days after from |  |
| **days** | [**Array&lt;AiOrdersUpdateRequestDaysInner&gt;**](AiOrdersUpdateRequestDaysInner.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiOrdersUpdateRequest.new(
  project_id: null,
  platform: null,
  currency: null,
  from: null,
  to: null,
  days: null
)
```


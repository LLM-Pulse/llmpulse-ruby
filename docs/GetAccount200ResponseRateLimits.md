# LLMPulse::GetAccount200ResponseRateLimits

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **requests_per_minute** | **Integer** | The ceiling enforced for the API key used on this call, which may be above the 300/min default. | [optional] |
| **write_requests_per_minute** | **Integer** | Flat ceiling on write requests, the same for every key. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GetAccount200ResponseRateLimits.new(
  requests_per_minute: null,
  write_requests_per_minute: null
)
```


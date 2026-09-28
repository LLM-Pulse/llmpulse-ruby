# LLMPulse::GetAccount200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **plan** | **String** | Plan key (starter, growth, scale, ...) | [optional] |
| **plan_name** | **String** | Display name of the plan to show people (e.g. Scale++ for the scaleplusplus key) | [optional] |
| **tracking_frequency** | **String** | How often prompts run (weekly, daily, monthly, ...) | [optional] |
| **role** | **String** | Whether the key belongs to the account owner or a team member | [optional] |
| **subscription** | [**GetAccount200ResponseSubscription**](GetAccount200ResponseSubscription.md) |  | [optional] |
| **limits** | [**GetAccount200ResponseLimits**](GetAccount200ResponseLimits.md) |  | [optional] |
| **rate_limits** | [**GetAccount200ResponseRateLimits**](GetAccount200ResponseRateLimits.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GetAccount200Response.new(
  plan: null,
  plan_name: null,
  tracking_frequency: null,
  role: null,
  subscription: null,
  limits: null,
  rate_limits: null,
  request_id: null
)
```


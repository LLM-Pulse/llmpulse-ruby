# LLMPulse::GetAccount200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **plan** | **String** | Plan key (starter, growth, scale, ...). Absent for a key limited to some projects. | [optional] |
| **plan_name** | **String** | Display name of the plan to show people (e.g. Scale++ for the scaleplusplus key). Absent for a key limited to some projects. | [optional] |
| **tracking_frequency** | **String** | How often prompts run (weekly, daily, monthly, ...) | [optional] |
| **role** | **String** | Whether the key belongs to the account owner or a team member | [optional] |
| **api_key_project_ids** | **Array&lt;Integer&gt;** | The projects the calling API key is limited to; null for a key that sees the whole account, and for OAuth | [optional] |
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
  api_key_project_ids: null,
  subscription: null,
  limits: null,
  rate_limits: null,
  request_id: null
)
```


# LLMPulse::GetAccount200ResponseLimits

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompts** | [**AccountQuota**](AccountQuota.md) |  | [optional] |
| **projects** | [**AccountQuota**](AccountQuota.md) |  | [optional] |
| **competitors_per_project** | [**AccountCapacity**](AccountCapacity.md) |  | [optional] |
| **intelligence_tasks** | [**AccountQuota**](AccountQuota.md) |  | [optional] |
| **team_members** | [**AccountCapacity**](AccountCapacity.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GetAccount200ResponseLimits.new(
  prompts: null,
  projects: null,
  competitors_per_project: null,
  intelligence_tasks: null,
  team_members: null
)
```


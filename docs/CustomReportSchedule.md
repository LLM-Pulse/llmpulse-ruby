# LLMPulse::CustomReportSchedule

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **enabled** | **Boolean** |  |  |
| **day_of_week** | **Integer** | 0 (Sunday) to 6 (Saturday) | [optional] |
| **hour** | **Integer** |  | [optional] |
| **timezone** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CustomReportSchedule.new(
  enabled: null,
  day_of_week: null,
  hour: null,
  timezone: null
)
```


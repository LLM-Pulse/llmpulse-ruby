# LLMPulse::GeoAuditUpdateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **cadence** | **String** |  | [optional] |
| **schedule_day** | **Integer** | Weekly: 0 (Sunday) to 6. Monthly: 1 to 28. | [optional] |
| **schedule_hour** | **Integer** | Hour of the day, 0 to 23, in the audit time zone | [optional] |
| **status** | **String** | paused stops scheduled runs, active resumes them, archived is the same as DELETE | [optional] |
| **email_alerts** | **Boolean** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAuditUpdateRequest.new(
  project_id: null,
  cadence: null,
  schedule_day: null,
  schedule_hour: null,
  status: null,
  email_alerts: null
)
```


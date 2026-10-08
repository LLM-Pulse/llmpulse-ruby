# LLMPulse::GeoAudit

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Stable audit id | [optional] |
| **audit_type** | **String** |  | [optional] |
| **target** | **String** | The audited domain (site-wide types) or page URL, normalized | [optional] |
| **country_code** | **String** |  | [optional] |
| **cadence** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **paused_reason** | **String** | user, or unreachable when three runs in a row could not reach the site | [optional] |
| **schedule** | [**GeoAuditSchedule**](GeoAuditSchedule.md) |  | [optional] |
| **next_run_at** | **Time** |  | [optional] |
| **email_alerts** | **Boolean** |  | [optional] |
| **recurring_available** | **Boolean** | Whether this audit type can run weekly or monthly | [optional] |
| **checks_tracked** | **Boolean** | Whether runs of this type produce findings and issues, or a score only | [optional] |
| **latest_run** | [**GeoAuditRun**](GeoAuditRun.md) |  | [optional] |
| **open_issues** | **Integer** |  | [optional] |
| **open_critical_issues** | **Integer** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **app_url** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAudit.new(
  id: null,
  audit_type: null,
  target: null,
  country_code: null,
  cadence: null,
  status: null,
  paused_reason: null,
  schedule: null,
  next_run_at: null,
  email_alerts: null,
  recurring_available: null,
  checks_tracked: null,
  latest_run: null,
  open_issues: null,
  open_critical_issues: null,
  created_at: null,
  app_url: null
)
```


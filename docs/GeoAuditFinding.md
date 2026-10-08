# LLMPulse::GeoAuditFinding

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **check_key** | **String** | Stable key of the check within its audit type | [optional] |
| **check_title** | **String** |  | [optional] |
| **subject_key** | **String** | What the check is about (site for site-wide checks, a bot slug for robots.txt bot checks) | [optional] |
| **subject** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **severity** | **String** |  | [optional] |
| **evidence** | **Object** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAuditFinding.new(
  check_key: null,
  check_title: null,
  subject_key: null,
  subject: null,
  status: null,
  severity: null,
  evidence: null
)
```


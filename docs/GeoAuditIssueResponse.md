# LLMPulse::GeoAuditIssueResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **check_key** | **String** |  | [optional] |
| **check_title** | **String** |  | [optional] |
| **subject_key** | **String** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **severity** | **String** |  | [optional] |
| **state** | **String** |  | [optional] |
| **badge** | **String** | How the latest comparable run moved the issue | [optional] |
| **accepted** | **Boolean** |  | [optional] |
| **accepted_at** | **Time** |  | [optional] |
| **regression_count** | **Integer** |  | [optional] |
| **evidence** | **Object** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |
| **project_id** | **Integer** |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAuditIssueResponse.new(
  id: null,
  check_key: null,
  check_title: null,
  subject_key: null,
  subject: null,
  severity: null,
  state: null,
  badge: null,
  accepted: null,
  accepted_at: null,
  regression_count: null,
  evidence: null,
  updated_at: null,
  project_id: null,
  request_id: null
)
```


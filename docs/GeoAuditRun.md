# LLMPulse::GeoAuditRun

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **sequence** | **Integer** | Run number within the audit, starting at 1 | [optional] |
| **status** | **String** |  | [optional] |
| **trigger** | **String** |  | [optional] |
| **score** | **Float** |  | [optional] |
| **grade** | **String** |  | [optional] |
| **score_delta** | **Float** | Score change against the previous completed run | [optional] |
| **comparable_to_previous** | **Boolean** | False when the checks or the audit settings changed since the previous run, so a diff may reflect that change | [optional] |
| **new_issues** | **Integer** |  | [optional] |
| **fixed_issues** | **Integer** |  | [optional] |
| **regressed_issues** | **Integer** |  | [optional] |
| **error** | **String** |  | [optional] |
| **engine_version** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **finished_at** | **Time** |  | [optional] |
| **app_url** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAuditRun.new(
  sequence: null,
  status: null,
  trigger: null,
  score: null,
  grade: null,
  score_delta: null,
  comparable_to_previous: null,
  new_issues: null,
  fixed_issues: null,
  regressed_issues: null,
  error: null,
  engine_version: null,
  created_at: null,
  finished_at: null,
  app_url: null
)
```


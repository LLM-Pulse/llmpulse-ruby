# LLMPulse::StudySummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **title** | **String** |  |  |
| **study_type** | **String** | brand_set, sector, geo, topic or custom |  |
| **cadence** | **String** | one_shot or monthly |  |
| **status** | **String** | active or archived |  |
| **project_id** | **Integer** | The project the study is attached to; null for an account-level study |  |
| **subjects_count** | **Integer** |  |  |
| **ai_models** | **Array&lt;String&gt;** | Analyst models the study runs on |  |
| **output_language_code** | **String** | ISO 639-1 code of the language the reports are written in |  |
| **created_at** | **Time** |  |  |
| **last_report_at** | **Time** | When the latest report started; null before the first one |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::StudySummary.new(
  id: null,
  title: null,
  study_type: null,
  cadence: null,
  status: null,
  project_id: null,
  subjects_count: null,
  ai_models: null,
  output_language_code: null,
  created_at: null,
  last_report_at: null
)
```


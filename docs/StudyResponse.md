# LLMPulse::StudyResponse

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
| **brief** | **String** | What the study asks the analyst models; null when none was written |  |
| **subjects** | **Array&lt;String&gt;** | Names of the subjects it compares |  |
| **dimensions** | **Array&lt;String&gt;** | Keys of the dimensions it scores, as the dimension filter takes them |  |
| **reports** | [**Array&lt;ReputationReportSummary&gt;**](ReputationReportSummary.md) | The 24 latest reports, newest first |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::StudyResponse.new(
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
  last_report_at: null,
  brief: null,
  subjects: null,
  dimensions: null,
  reports: null,
  request_id: null
)
```


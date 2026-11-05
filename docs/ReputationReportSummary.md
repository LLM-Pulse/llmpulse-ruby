# LLMPulse::ReputationReportSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Report id for GET /reputation/reports/{id} |  |
| **status** | **String** |  |  |
| **created_at** | **Time** |  |  |
| **processed_at** | **Time** |  | [optional] |
| **available_models** | **Array&lt;String&gt;** | Analyst models that produced data |  |
| **missing_models** | **Array&lt;String&gt;** | Analyst models with no data yet |  |
| **error_message** | **String** | Why the report failed; null unless status is failed | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ReputationReportSummary.new(
  id: null,
  status: null,
  created_at: null,
  processed_at: null,
  available_models: null,
  missing_models: null,
  error_message: null
)
```


# LLMPulse::RecommendationSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **project_id** | **Integer** |  |  |
| **recommendation_type** | **String** |  |  |
| **status** | **String** |  |  |
| **error_message** | **String** | Set only when status is failed |  |
| **generated_at** | **Time** | Null until the generation completes |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **total_recommendations** | **Integer** |  |  |
| **high_priority_count** | **Integer** |  |  |
| **summary** | [**RecommendationSummarySummary**](RecommendationSummarySummary.md) |  |  |
| **context** | **Object** | Generation context and run diagnostics as stored; empty until the generation completes. Its keys are not a stable contract |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::RecommendationSummary.new(
  id: null,
  project_id: null,
  recommendation_type: null,
  status: null,
  error_message: null,
  generated_at: null,
  created_at: null,
  updated_at: null,
  total_recommendations: null,
  high_priority_count: null,
  summary: null,
  context: null
)
```


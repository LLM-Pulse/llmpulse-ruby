# LLMPulse::RecommendationDetailResponse

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
| **summary** | [**RecommendationDetailResponseSummary**](RecommendationDetailResponseSummary.md) |  |  |
| **context** | **Object** | Generation context and run diagnostics as stored; empty until the generation completes. Its keys are not a stable contract |  |
| **report_data** | **Hash&lt;String, Object&gt;** | The stored run, including the evidence indices (prompts_index, citations_index, own_content_index and others) that the source_refs codes of the items point to. Its keys are not a stable contract |  |
| **item_counts** | [**RecommendationDetailResponseItemCounts**](RecommendationDetailResponseItemCounts.md) |  |  |
| **items** | [**Array&lt;RecommendationItem&gt;**](RecommendationItem.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::RecommendationDetailResponse.new(
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
  context: null,
  report_data: null,
  item_counts: null,
  items: null,
  request_id: null
)
```


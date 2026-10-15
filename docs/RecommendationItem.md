# LLMPulse::RecommendationItem

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **recommendation_id** | **Integer** |  |  |
| **recommendation_type** | **String** |  |  |
| **category** | **String** |  |  |
| **title** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **priority** | **String** |  |  |
| **estimated_impact** | **String** |  | [optional] |
| **action_items** | **Array&lt;String&gt;** |  |  |
| **source_refs** | **Array&lt;String&gt;** | Evidence codes (e.g. P1, C2) resolved in resolved_source_refs |  |
| **status** | **String** |  |  |
| **status_changed_at** | **Time** |  | [optional] |
| **position** | **Integer** |  |  |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **resolved_source_refs** | **Array&lt;Hash&lt;String, Object&gt;&gt;** | The evidence each source_refs code points to (prompt, citation or own page) | [optional] |
| **unresolved_source_refs** | **Array&lt;String&gt;** | Present only when a code points to no stored evidence | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::RecommendationItem.new(
  id: null,
  recommendation_id: null,
  recommendation_type: null,
  category: null,
  title: null,
  description: null,
  priority: null,
  estimated_impact: null,
  action_items: null,
  source_refs: null,
  status: null,
  status_changed_at: null,
  position: null,
  metadata: null,
  created_at: null,
  updated_at: null,
  resolved_source_refs: null,
  unresolved_source_refs: null
)
```


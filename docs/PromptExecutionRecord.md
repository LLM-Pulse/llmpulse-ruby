# LLMPulse::PromptExecutionRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **prompt_id** | **Integer** |  |  |
| **executed_at** | **Time** | Null while the answer is still pending |  |
| **duration_ms** | **Float** |  |  |
| **success** | **Boolean** | Null while the answer is still pending |  |
| **model** | **String** |  |  |
| **fan_out_queries** | **Array&lt;String&gt;** | Sub-queries the model issued while answering; null when the model reports none |  |
| **has_mention** | **Boolean** |  |  |
| **has_citation** | **Boolean** |  |  |
| **mentions_count** | **Integer** | 1 when the answer mentions the brand, otherwise 0 |  |
| **citations_count** | **Integer** | 1 when the answer cites the brand, otherwise 0 |  |
| **app_url** | **String** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptExecutionRecord.new(
  id: null,
  prompt_id: null,
  executed_at: null,
  duration_ms: null,
  success: null,
  model: null,
  fan_out_queries: null,
  has_mention: null,
  has_citation: null,
  mentions_count: null,
  citations_count: null,
  app_url: null
)
```


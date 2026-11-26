# LLMPulse::CitedUrlOccurrencesResponseAllOfData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **source_id** | **Integer** |  |  |
| **answer_id** | **Integer** |  |  |
| **prompt_execution_id** | **Integer** | Same as answer_id |  |
| **prompt_id** | **Integer** |  |  |
| **prompt_text** | **String** |  |  |
| **model** | **String** |  |  |
| **executed_at** | **Time** |  |  |
| **citation_position** | **Integer** | Rank of the citation in the answer; 0 for a background source reference |  |
| **url** | **String** | Normalized cited URL |  |
| **domain** | **String** |  |  |
| **source_type** | **String** | owned, competitor or third_party |  |
| **response_excerpt** | **String** | The first 600 characters of the answer |  |
| **response_truncated** | **Boolean** |  |  |
| **fan_out_queries** | **Array&lt;String&gt;** | Sub-queries the model issued while answering; null when the model reports none |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitedUrlOccurrencesResponseAllOfData.new(
  source_id: null,
  answer_id: null,
  prompt_execution_id: null,
  prompt_id: null,
  prompt_text: null,
  model: null,
  executed_at: null,
  citation_position: null,
  url: null,
  domain: null,
  source_type: null,
  response_excerpt: null,
  response_truncated: null,
  fan_out_queries: null
)
```


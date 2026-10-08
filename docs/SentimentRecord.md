# LLMPulse::SentimentRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **prompt_execution_id** | **Integer** |  |  |
| **prompt_text** | **String** |  |  |
| **model** | **String** |  |  |
| **analysis** | **String** |  |  |
| **score** | **Float** | From -1 (very negative) to 1 (very positive) |  |
| **comment** | **String** |  |  |
| **topics** | **String** | Comma-separated topics |  |
| **competitor_id** | **Integer** | Null for a sentiment about the project&#39;s own brand |  |
| **competitor_name** | **String** | Null for a sentiment about the project&#39;s own brand |  |
| **is_brand_sentiment** | **Boolean** |  |  |
| **executed_at** | **Time** |  |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SentimentRecord.new(
  id: null,
  prompt_execution_id: null,
  prompt_text: null,
  model: null,
  analysis: null,
  score: null,
  comment: null,
  topics: null,
  competitor_id: null,
  competitor_name: null,
  is_brand_sentiment: null,
  executed_at: null,
  created_at: null
)
```


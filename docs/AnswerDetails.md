# LLMPulse::AnswerDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **prompt_id** | **Integer** |  | [optional] |
| **prompt_text** | **String** |  | [optional] |
| **model** | **String** |  | [optional] |
| **response** | **String** |  | [optional] |
| **response_truncated** | **Boolean** |  | [optional] |
| **executed_at** | **Time** |  | [optional] |
| **duration_ms** | **Integer** |  | [optional] |
| **success** | **Boolean** |  | [optional] |
| **fan_out_queries** | **Array&lt;String&gt;** |  | [optional] |
| **mentions** | **Array&lt;Object&gt;** |  | [optional] |
| **citations** | **Array&lt;Object&gt;** |  | [optional] |
| **competitor_mentions** | **Array&lt;Object&gt;** |  | [optional] |
| **competitor_citations** | **Array&lt;Object&gt;** |  | [optional] |
| **sentiments** | **Array&lt;Object&gt;** |  | [optional] |
| **sources** | **Array&lt;Object&gt;** |  | [optional] |
| **shopping_products** | **Array&lt;Object&gt;** |  | [optional] |
| **brand_entities** | **Array&lt;Object&gt;** |  | [optional] |
| **local_businesses** | **Array&lt;Object&gt;** |  | [optional] |
| **locale** | [**AnswerDetailsLocale**](AnswerDetailsLocale.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AnswerDetails.new(
  id: null,
  prompt_id: null,
  prompt_text: null,
  model: null,
  response: null,
  response_truncated: null,
  executed_at: null,
  duration_ms: null,
  success: null,
  fan_out_queries: null,
  mentions: null,
  citations: null,
  competitor_mentions: null,
  competitor_citations: null,
  sentiments: null,
  sources: null,
  shopping_products: null,
  brand_entities: null,
  local_businesses: null,
  locale: null
)
```


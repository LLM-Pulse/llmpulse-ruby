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
| **duration_ms** | **Float** | Milliseconds, rounded to one decimal place | [optional] |
| **success** | **Boolean** | Null while the answer is still pending | [optional] |
| **no_result** | **Boolean** | True for a sentinel non-answer (the provider returned nothing after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics | [optional] |
| **fan_out_queries** | **Array&lt;String&gt;** |  | [optional] |
| **mentions** | **Array&lt;Object&gt;** |  | [optional] |
| **citations** | **Array&lt;Object&gt;** |  | [optional] |
| **competitor_mentions** | **Array&lt;Object&gt;** |  | [optional] |
| **competitor_citations** | **Array&lt;Object&gt;** |  | [optional] |
| **sentiments** | **Array&lt;Object&gt;** | Needs the Growth plan or above; left out below it and named in plan_required_fields | [optional] |
| **sources** | **Array&lt;Object&gt;** |  | [optional] |
| **shopping_products** | **Array&lt;Object&gt;** | Needs the Scale plan or above; left out below it and named in plan_required_fields | [optional] |
| **brand_entities** | **Array&lt;Object&gt;** |  | [optional] |
| **local_businesses** | **Array&lt;Object&gt;** |  | [optional] |
| **locale** | [**AnswerDetailsLocale**](AnswerDetailsLocale.md) |  | [optional] |
| **plan_required_fields** | **Array&lt;String&gt;** | The fields left out of this answer because the account&#39;s plan does not include them (sentiments below Growth, shopping_products below Scale). Always present, empty when nothing is left out |  |
| **app_url** | **String** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project | [optional] |
| **request_id** | **String** |  | [optional] |

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
  no_result: null,
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
  locale: null,
  plan_required_fields: null,
  app_url: null,
  request_id: null
)
```


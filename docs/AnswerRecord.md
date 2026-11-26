# LLMPulse::AnswerRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **prompt_id** | **Integer** |  |  |
| **prompt_text** | **String** |  |  |
| **model** | **String** |  |  |
| **executed_at** | **Time** |  |  |
| **duration_ms** | **Float** | Milliseconds our pipeline spent processing the collected answer, rounded to one decimal place |  |
| **no_result** | **Boolean** | True for a sentinel non-answer (no answer could be collected after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics |  |
| **no_result_reason** | **String** | Present only when no_result is true. declined &#x3D; the model declined to answer and response holds its reply; no_answer &#x3D; no answer could be collected | [optional] |
| **mentions_count** | **Integer** | Mentions of your brand in the answer |  |
| **citations_count** | **Integer** | Citations of your brand in the answer |  |
| **app_url** | **String** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |  |
| **response** | **String** | The answer text, cut to 10,000 characters (without query) | [optional] |
| **response_truncated** | **Boolean** | Whether response was cut (without query) | [optional] |
| **snippet** | **String** | The text around the first match (with query) | [optional] |
| **match_count** | **Integer** | Matches of query in the answer (with query) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AnswerRecord.new(
  id: null,
  prompt_id: null,
  prompt_text: null,
  model: null,
  executed_at: null,
  duration_ms: null,
  no_result: null,
  no_result_reason: null,
  mentions_count: null,
  citations_count: null,
  app_url: null,
  response: null,
  response_truncated: null,
  snippet: null,
  match_count: null
)
```


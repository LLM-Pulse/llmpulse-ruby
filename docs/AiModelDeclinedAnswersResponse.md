# LLMPulse::AiModelDeclinedAnswersResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **from** | **Time** | Start of the tracking period holding the first day asked for |  |
| **to** | **Time** |  |  |
| **model** | **String** | The model the counts are for |  |
| **cadence** | **String** | The account&#39;s current tracking cadence: daily, weekly or monthly. Chart periods before a switch from weekly to daily stay weekly. |  |
| **filters** | [**AiModelDeclinedAnswersResponseFilters**](AiModelDeclinedAnswersResponseFilters.md) |  | [optional] |
| **summary** | [**AiModelDeclinedAnswersResponseSummary**](AiModelDeclinedAnswersResponseSummary.md) |  |  |
| **chart** | [**Array&lt;AiModelDeclinedAnswersResponseChartInner&gt;**](AiModelDeclinedAnswersResponseChartInner.md) | One point per tracking period holding an answer, oldest first. A period without answers has no point; a period with answers and no declines is a real 0. |  |
| **by_prompt** | [**AiModelDeclinedAnswersResponseByPrompt**](AiModelDeclinedAnswersResponseByPrompt.md) |  |  |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelDeclinedAnswersResponse.new(
  project_id: null,
  from: null,
  to: null,
  model: null,
  cadence: null,
  filters: null,
  summary: null,
  chart: null,
  by_prompt: null,
  request_id: null
)
```


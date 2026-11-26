# LLMPulse::AiOverviewResultsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **from** | **Time** |  |  |
| **to** | **Time** |  |  |
| **filters** | [**AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  |  |
| **granularity** | **String** |  |  |
| **summary** | [**AiOverviewResultCounts**](AiOverviewResultCounts.md) |  |  |
| **chart** | [**Array&lt;AiOverviewResultsResponseChartInner&gt;**](AiOverviewResultsResponseChartInner.md) | One point per period of the window, oldest first, 0 included |  |
| **by_prompt** | [**AiOverviewResultsResponseByPrompt**](AiOverviewResultsResponseByPrompt.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiOverviewResultsResponse.new(
  project_id: null,
  from: null,
  to: null,
  filters: null,
  granularity: null,
  summary: null,
  chart: null,
  by_prompt: null,
  request_id: null
)
```


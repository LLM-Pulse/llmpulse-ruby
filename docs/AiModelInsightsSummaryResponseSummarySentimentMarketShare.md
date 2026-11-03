# LLMPulse::AiModelInsightsSummaryResponseSummarySentimentMarketShare

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **actors** | [**Array&lt;AiModelSentimentMatrixActor&gt;**](AiModelSentimentMatrixActor.md) | The project and each competitor with a sentiment verdict in the window (only the competitors given in competitors, when it is given), by total_sentiments descending | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelInsightsSummaryResponseSummarySentimentMarketShare.new(
  actors: null
)
```


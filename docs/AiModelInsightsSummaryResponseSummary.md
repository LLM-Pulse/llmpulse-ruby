# LLMPulse::AiModelInsightsSummaryResponseSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **mentions_by_model** | [**AiModelInsightsSummaryResponseSummaryMentionsByModel**](AiModelInsightsSummaryResponseSummaryMentionsByModel.md) |  | [optional] |
| **citations_by_model** | [**AiModelInsightsSummaryResponseSummaryCitationsByModel**](AiModelInsightsSummaryResponseSummaryCitationsByModel.md) |  | [optional] |
| **brand_net_sentiment_by_model** | [**AiModelInsightsSummaryResponseSummaryBrandNetSentimentByModel**](AiModelInsightsSummaryResponseSummaryBrandNetSentimentByModel.md) |  | [optional] |
| **weighted_visibility_by_model** | [**AiModelInsightsSummaryResponseSummaryWeightedVisibilityByModel**](AiModelInsightsSummaryResponseSummaryWeightedVisibilityByModel.md) |  | [optional] |
| **mentions_market_share** | [**AiModelRateMatrix**](AiModelRateMatrix.md) |  | [optional] |
| **citations_market_share** | [**AiModelRateMatrix**](AiModelRateMatrix.md) |  | [optional] |
| **sentiment_market_share** | [**AiModelInsightsSummaryResponseSummarySentimentMarketShare**](AiModelInsightsSummaryResponseSummarySentimentMarketShare.md) |  | [optional] |
| **weighted_visibility_market_share** | [**AiModelInsightsSummaryResponseSummaryWeightedVisibilityMarketShare**](AiModelInsightsSummaryResponseSummaryWeightedVisibilityMarketShare.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelInsightsSummaryResponseSummary.new(
  mentions_by_model: null,
  citations_by_model: null,
  brand_net_sentiment_by_model: null,
  weighted_visibility_by_model: null,
  mentions_market_share: null,
  citations_market_share: null,
  sentiment_market_share: null,
  weighted_visibility_market_share: null
)
```


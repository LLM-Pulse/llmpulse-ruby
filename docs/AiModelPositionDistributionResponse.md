# LLMPulse::AiModelPositionDistributionResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **from** | **Time** |  |  |
| **to** | **Time** |  |  |
| **filters** | [**AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  |  |
| **granularity** | **String** |  |  |
| **brands** | [**Array&lt;AiModelPositionDistributionBrand&gt;**](AiModelPositionDistributionBrand.md) | The first brand (brand1, else the project) and the second (brand2, else the competitor with the most mentions, else the project), each left out when it has no mention in the window |  |
| **max_stacked_value** | **Integer** | The largest mentions count of one period across the brands, for a shared chart axis |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelPositionDistributionResponse.new(
  project_id: null,
  from: null,
  to: null,
  filters: null,
  granularity: null,
  brands: null,
  max_stacked_value: null,
  request_id: null
)
```


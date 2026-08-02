# LLMPulse::SummaryResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **granularity** | **String** |  | [optional] |
| **filters** | **Object** |  | [optional] |
| **series** | **Hash&lt;String, Array&lt;TimeseriesSeries&gt;&gt;** |  | [optional] |
| **request_id** | **String** |  | [optional] |
| **summary** | **Hash&lt;String, Array&lt;SummaryResponseAllOfSummaryValueInner&gt;&gt;** |  | [optional] |
| **position_distribution** | [**SummaryResponseAllOfPositionDistribution**](SummaryResponseAllOfPositionDistribution.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SummaryResponse.new(
  project_id: null,
  from: null,
  to: null,
  granularity: null,
  filters: null,
  series: null,
  request_id: null,
  summary: null,
  position_distribution: null
)
```


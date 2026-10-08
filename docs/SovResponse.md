# LLMPulse::SovResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **granularity** | **String** | day, week or month | [optional] |
| **filters** | [**MetricsFiltersEcho**](MetricsFiltersEcho.md) |  | [optional] |
| **periods** | [**Array&lt;SovResponsePeriodsInner&gt;**](SovResponsePeriodsInner.md) | Per-bucket sample size and completeness: mentions is the total the shares were computed on (1-3 mentions produce the 100/50/33.33 low-sample patterns); partial marks buckets still collecting data or clipped by the requested window; confidence and margin_of_error read the sample size. | [optional] |
| **sample** | [**SovResponseSample**](SovResponseSample.md) |  | [optional] |
| **over_time** | [**Array&lt;SovResponseOverTimeInner&gt;**](SovResponseOverTimeInner.md) |  | [optional] |
| **current** | [**Array&lt;SovResponseCurrentInner&gt;**](SovResponseCurrentInner.md) |  | [optional] |
| **breakdown** | [**Array&lt;SovResponseBreakdownInner&gt;**](SovResponseBreakdownInner.md) |  | [optional] |
| **others** | [**Array&lt;SovResponseOthersInner&gt;**](SovResponseOthersInner.md) | Actors ranked fifth and below, folded into the Others share of breakdown | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SovResponse.new(
  project_id: null,
  from: null,
  to: null,
  granularity: null,
  filters: null,
  periods: null,
  sample: null,
  over_time: null,
  current: null,
  breakdown: null,
  others: null,
  request_id: null
)
```


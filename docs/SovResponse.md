# LLMPulse::SovResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **periods** | [**Array&lt;SovResponsePeriodsInner&gt;**](SovResponsePeriodsInner.md) | Per-bucket sample size and completeness: mentions is the total the shares were computed on (1-3 mentions produce the 100/50/33.33 low-sample patterns); partial marks buckets still collecting data or clipped by the requested window. | [optional] |
| **over_time** | [**Array&lt;SovResponseOverTimeInner&gt;**](SovResponseOverTimeInner.md) |  | [optional] |
| **current** | [**Array&lt;SovResponseCurrentInner&gt;**](SovResponseCurrentInner.md) |  | [optional] |
| **breakdown** | [**Array&lt;SovResponseBreakdownInner&gt;**](SovResponseBreakdownInner.md) |  | [optional] |
| **others** | **Array&lt;Object&gt;** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SovResponse.new(
  project_id: null,
  periods: null,
  over_time: null,
  current: null,
  breakdown: null,
  others: null
)
```


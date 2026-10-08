# LLMPulse::SummaryResponseAllOfSummaryValueInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **actor** | [**Actor**](Actor.md) |  | [optional] |
| **metric** | **String** |  | [optional] |
| **total** | **Float** |  | [optional] |
| **aggregation** | **String** | How total combines the buckets | [optional] |
| **min** | **Float** |  | [optional] |
| **max** | **Float** |  | [optional] |
| **last** | **Float** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SummaryResponseAllOfSummaryValueInner.new(
  actor: null,
  metric: null,
  total: null,
  aggregation: null,
  min: null,
  max: null,
  last: null
)
```


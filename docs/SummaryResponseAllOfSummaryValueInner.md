# LLMPulse::SummaryResponseAllOfSummaryValueInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **actor** | [**Actor**](Actor.md) |  | [optional] |
| **metric** | **String** |  | [optional] |
| **total** | **Float** | Count metrics sum the buckets; rate, position and sentiment metrics average them. ai_visibility_score (weighted_visibility) is the window&#39;s points divided by its data days (the days with responses under the filters), the number the app shows, whatever the granularity. | [optional] |
| **aggregation** | **String** | How total combines the buckets (average for ai_visibility_score, a per-data-day score) | [optional] |
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


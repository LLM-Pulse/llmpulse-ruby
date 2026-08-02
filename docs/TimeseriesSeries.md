# LLMPulse::TimeseriesSeries

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **actor** | [**Actor**](Actor.md) |  | [optional] |
| **metric** | **String** |  | [optional] |
| **data** | [**Array&lt;TimeseriesPoint&gt;**](TimeseriesPoint.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TimeseriesSeries.new(
  actor: null,
  metric: null,
  data: null
)
```


# LLMPulse::TimeseriesPoint

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Date** | Calendar day in Europe/Madrid (YYYY-MM-DD). With granularity week or month it is the first day of the bucket (the Monday, or the 1st of the month). | [optional] |
| **value** | **Float** | Null when the metric has no value for the bucket, e.g. a rate, position or sentiment metric on a day without answers. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TimeseriesPoint.new(
  date: null,
  value: null
)
```


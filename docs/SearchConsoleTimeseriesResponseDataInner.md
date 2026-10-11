# LLMPulse::SearchConsoleTimeseriesResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Date** |  | [optional] |
| **impressions** | **Integer** |  | [optional] |
| **clicks** | **Integer** |  | [optional] |
| **ctr** | **Float** | 0..1 fraction | [optional] |
| **position** | **Float** | Impression-weighted average position | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleTimeseriesResponseDataInner.new(
  date: null,
  impressions: null,
  clicks: null,
  ctr: null,
  position: null
)
```


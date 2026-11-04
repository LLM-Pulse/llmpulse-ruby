# LLMPulse::OwnedMediaSummaryActivityPeriod

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Date** | Start date of the actual reporting period |  |
| **citations** | **Integer** |  |  |
| **yours** | **Integer** | Citations on owned profiles and content, null for provider&#x3D;overview |  |
| **other** | **Integer** | Citations not counted as yours, null for provider&#x3D;overview |  |
| **positive** | **Integer** | Citations whose AI answer sentiment is positive | [optional] |
| **neutral** | **Integer** | Citations whose AI answer sentiment is neutral or mixed | [optional] |
| **negative** | **Integer** | Citations whose AI answer sentiment is negative | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaSummaryActivityPeriod.new(
  date: null,
  citations: null,
  yours: null,
  other: null,
  positive: null,
  neutral: null,
  negative: null
)
```


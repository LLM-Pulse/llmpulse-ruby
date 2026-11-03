# LLMPulse::SearchConsoleOpportunitiesResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **query** | **String** |  | [optional] |
| **impressions** | **Integer** |  | [optional] |
| **clicks** | **Integer** |  | [optional] |
| **ctr** | **Float** | 0..1 fraction | [optional] |
| **position** | **Float** | Impression-weighted average position | [optional] |
| **potential_clicks** | **Integer** | Clicks a move into the top 3 would add at top_ctr (never negative); null when top_ctr is null | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleOpportunitiesResponseDataInner.new(
  query: null,
  impressions: null,
  clicks: null,
  ctr: null,
  position: null,
  potential_clicks: null
)
```


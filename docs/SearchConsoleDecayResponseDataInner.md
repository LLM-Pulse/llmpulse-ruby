# LLMPulse::SearchConsoleDecayResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key** | **String** | The page URL or query | [optional] |
| **clicks** | **Integer** |  | [optional] |
| **clicks_previous** | **Integer** |  | [optional] |
| **clicks_change** | **Integer** | clicks minus clicks_previous (negative) | [optional] |
| **clicks_change_pct** | **Float** |  | [optional] |
| **impressions** | **Integer** |  | [optional] |
| **impressions_previous** | **Integer** |  | [optional] |
| **position** | **Float** | Null when the key had no impressions in the window | [optional] |
| **position_previous** | **Float** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleDecayResponseDataInner.new(
  key: null,
  clicks: null,
  clicks_previous: null,
  clicks_change: null,
  clicks_change_pct: null,
  impressions: null,
  impressions_previous: null,
  position: null,
  position_previous: null
)
```


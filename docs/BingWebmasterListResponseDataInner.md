# LLMPulse::BingWebmasterListResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key** | **String** | The page URL or the query | [optional] |
| **impressions** | **Integer** |  | [optional] |
| **clicks** | **Integer** |  | [optional] |
| **ctr** | **Float** | 0..1 fraction | [optional] |
| **avg_impression_position** | **Float** | Average position when shown, weighted by impressions (lower is better) | [optional] |
| **avg_click_position** | **Float** | Average position when clicked, weighted by clicks. Null without clicks. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::BingWebmasterListResponseDataInner.new(
  key: null,
  impressions: null,
  clicks: null,
  ctr: null,
  avg_impression_position: null,
  avg_click_position: null
)
```


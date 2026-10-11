# LLMPulse::SearchConsoleListResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key** | **String** | The query or page URL | [optional] |
| **impressions** | **Integer** |  | [optional] |
| **clicks** | **Integer** |  | [optional] |
| **ctr** | **Float** | 0..1 fraction | [optional] |
| **position** | **Float** | Impression-weighted average position | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleListResponseDataInner.new(
  key: null,
  impressions: null,
  clicks: null,
  ctr: null,
  position: null
)
```


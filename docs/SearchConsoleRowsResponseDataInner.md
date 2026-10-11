# LLMPulse::SearchConsoleRowsResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Date** |  | [optional] |
| **country** | **String** |  | [optional] |
| **device** | **String** |  | [optional] |
| **page** | **String** |  | [optional] |
| **query** | **String** |  | [optional] |
| **search_appearance** | **String** |  | [optional] |
| **impressions** | **Integer** |  | [optional] |
| **clicks** | **Integer** |  | [optional] |
| **ctr** | **Float** | 0..1 fraction | [optional] |
| **position** | **Float** | Impression-weighted average position | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleRowsResponseDataInner.new(
  date: null,
  country: null,
  device: null,
  page: null,
  query: null,
  search_appearance: null,
  impressions: null,
  clicks: null,
  ctr: null,
  position: null
)
```


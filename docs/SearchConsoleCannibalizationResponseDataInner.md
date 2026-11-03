# LLMPulse::SearchConsoleCannibalizationResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **query** | **String** |  | [optional] |
| **impressions** | **Integer** |  | [optional] |
| **clicks** | **Integer** |  | [optional] |
| **ctr** | **Float** | 0..1 fraction | [optional] |
| **position** | **Float** | Impression-weighted average position | [optional] |
| **pages** | [**Array&lt;SearchConsoleCannibalizationResponseDataInnerPagesInner&gt;**](SearchConsoleCannibalizationResponseDataInnerPagesInner.md) | Pages taking at least min_share of the query&#39;s impressions, most impressions first | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleCannibalizationResponseDataInner.new(
  query: null,
  impressions: null,
  clicks: null,
  ctr: null,
  position: null,
  pages: null
)
```


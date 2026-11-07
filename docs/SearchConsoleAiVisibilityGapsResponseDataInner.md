# LLMPulse::SearchConsoleAiVisibilityGapsResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **query** | **String** |  | [optional] |
| **impressions** | **Integer** |  | [optional] |
| **clicks** | **Integer** |  | [optional] |
| **ctr** | **Float** | 0..1 fraction | [optional] |
| **position** | **Float** | Impression-weighted average position | [optional] |
| **prompt_id** | **Integer** | The project&#39;s prompt the query matches (see match_type); null when no prompt matches | [optional] |
| **responses** | **Integer** | AI answers the matching prompt got in the window over the account&#39;s enabled models; null when no prompt matches | [optional] |
| **brand_visibility** | **Float** | Brand Visibility of the matching prompt in the window, percent (0-100) of its AI answers that mention the brand, over the account&#39;s enabled models; null when no prompt matches or it has no answer | [optional] |
| **match_type** | **String** | How the query matched: prompt (the same text as the prompt) or fan_out (the same text as a search the prompt&#39;s AI answers ran in the window); null when no prompt matches | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleAiVisibilityGapsResponseDataInner.new(
  query: null,
  impressions: null,
  clicks: null,
  ctr: null,
  position: null,
  prompt_id: null,
  responses: null,
  brand_visibility: null,
  match_type: null
)
```


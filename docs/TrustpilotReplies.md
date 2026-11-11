# LLMPulse::TrustpilotReplies

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **reviews_held** | **Integer** | Reviews held for the profile | [optional] |
| **replied_count** | **Integer** | Reviews held that the brand replied to | [optional] |
| **not_replied_count** | **Integer** | Reviews held that the brand has not replied to | [optional] |
| **reply_rate_pct** | **Float** | replied_count over reviews_held, on a 0-100 scale; null when no review is held | [optional] |
| **median_reply_hours** | **Float** | Median hours from publication to reply over the replied reviews held that carry both dates (a reply dated before its review is left out); null when there is none | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TrustpilotReplies.new(
  reviews_held: null,
  replied_count: null,
  not_replied_count: null,
  reply_rate_pct: null,
  median_reply_hours: null
)
```


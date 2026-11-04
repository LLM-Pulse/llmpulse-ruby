# LLMPulse::RedditBrandShare

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **actor_id** | **Integer** |  |  |
| **actor_name** | **String** |  |  |
| **is_brand** | **Boolean** |  |  |
| **citations** | **Integer** |  |  |
| **share_pct** | **Float** | Percentage (0-100) among the tracked brand and competitors with cited mentions |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::RedditBrandShare.new(
  actor_id: null,
  actor_name: null,
  is_brand: null,
  citations: null,
  share_pct: null
)
```


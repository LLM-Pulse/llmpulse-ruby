# LLMPulse::OwnedMediaKpiChanges

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Float** |  | [optional] |
| **yours** | **Float** |  | [optional] |
| **your_profile** | **Float** |  | [optional] |
| **your_content** | **Float** |  | [optional] |
| **share_pct** | **Float** |  | [optional] |
| **unique_subreddits** | **Float** | Percent change in unique subreddits; null when the previous value cannot be compared | [optional] |
| **unique_authors** | **Float** | Percent change in unique authors; null when the previous value cannot be compared | [optional] |
| **positive_pct** | **Float** | Percentage-point change in positive sentiment; null when the previous period has no citations | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaKpiChanges.new(
  total: null,
  yours: null,
  your_profile: null,
  your_content: null,
  share_pct: null,
  unique_subreddits: null,
  unique_authors: null,
  positive_pct: null
)
```


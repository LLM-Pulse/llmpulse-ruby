# LLMPulse::OwnedMediaKpis

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total** | **Integer** | Citations of the platform in the window, yours and everyone else&#39;s | [optional] |
| **yours** | **Integer** | Citations of your own profiles and their content | [optional] |
| **your_profile** | **Integer** | Citations of your profile or channel pages. Null for mobile_apps and overview | [optional] |
| **your_content** | **Integer** | Citations of your posts or videos. Null for mobile_apps and overview | [optional] |
| **share_pct** | **Float** | yours as a percentage of total (0-100) | [optional] |
| **unique_subreddits** | **Integer** | Number of cited subreddits (provider&#x3D;reddit; null or omitted for other providers) | [optional] |
| **unique_authors** | **Integer** | Number of cited Reddit authors (provider&#x3D;reddit; null or omitted for other providers) | [optional] |
| **positive_pct** | **Float** | Positive sentiment among rated Reddit citations, as a percentage (provider&#x3D;reddit; null or omitted for other providers) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaKpis.new(
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


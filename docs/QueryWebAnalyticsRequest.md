# LLMPulse::QueryWebAnalyticsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **query** | **Object** | The query in the provider&#39;s native format (see GET /web_analytics/schema): a JSON object for GA4, Adobe, Matomo, Plausible and Piano; for PostHog, {\&quot;query\&quot;: \&quot;&lt;HogQL&gt;\&quot;} or the HogQL string. Deliberately untyped so generated clients accept either shape. |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::QueryWebAnalyticsRequest.new(
  project_id: null,
  query: null
)
```


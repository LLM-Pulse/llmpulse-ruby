# LLMPulse::AiTrafficResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **provider** | **String** | The connected provider: google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo or piano |  |
| **from** | **Date** |  |  |
| **to** | **Date** |  |  |
| **granularity** | **String** |  |  |
| **totals** | [**AiTrafficResponseTotals**](AiTrafficResponseTotals.md) |  |  |
| **by_source** | [**Array&lt;AiTrafficResponseBySourceInner&gt;**](AiTrafficResponseBySourceInner.md) | One row per AI source with traffic in the window, most sessions first |  |
| **timeseries** | **Hash&lt;String, Hash&lt;String, Integer&gt;&gt;** | Sessions keyed by AI source slug, then by the first day of the period (YYYY-MM-DD); a period without traffic is left out |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiTrafficResponse.new(
  project_id: null,
  provider: null,
  from: null,
  to: null,
  granularity: null,
  totals: null,
  by_source: null,
  timeseries: null,
  request_id: null
)
```


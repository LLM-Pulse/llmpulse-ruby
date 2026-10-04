# LLMPulse::AiOrdersResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **platform** | **String** |  |  |
| **currency** | **String** | ISO 4217 code of the most recent stored day; null when the window holds no stored order |  |
| **from** | **Date** |  |  |
| **to** | **Date** |  |  |
| **totals** | [**AiOrdersResponseTotals**](AiOrdersResponseTotals.md) |  |  |
| **by_source** | [**Array&lt;AiOrdersResponseBySourceInner&gt;**](AiOrdersResponseBySourceInner.md) | One row per AI assistant, highest revenue first |  |
| **series** | [**Array&lt;AiOrdersResponseSeriesInner&gt;**](AiOrdersResponseSeriesInner.md) | Days that have stored orders, oldest first |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiOrdersResponse.new(
  project_id: null,
  platform: null,
  currency: null,
  from: null,
  to: null,
  totals: null,
  by_source: null,
  series: null,
  request_id: null
)
```


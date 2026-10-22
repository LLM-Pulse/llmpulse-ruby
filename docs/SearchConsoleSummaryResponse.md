# LLMPulse::SearchConsoleSummaryResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional] |
| **from** | **Date** |  | [optional] |
| **to** | **Date** |  | [optional] |
| **data_through** | **Date** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional] |
| **totals** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional] |
| **dimension** | **String** | Present when a breakdown was requested | [optional] |
| **breakdown** | [**Array&lt;SearchConsoleSummaryResponseBreakdownInner&gt;**](SearchConsoleSummaryResponseBreakdownInner.md) | Present when a breakdown was requested, sorted by impressions descending | [optional] |
| **breakdown_truncated** | **Boolean** | Present (true) when limit or Google&#39;s 25,000-row maximum left breakdown rows out, so they add up to less than totals | [optional] |
| **request_id** | **String** |  | [optional] |
| **properties** | [**Array&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional] |
| **excluded_properties** | [**Array&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them | [optional] |
| **property_errors** | [**Array&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleSummaryResponse.new(
  project_id: null,
  property: null,
  from: null,
  to: null,
  data_through: null,
  totals: null,
  dimension: null,
  breakdown: null,
  breakdown_truncated: null,
  request_id: null,
  properties: null,
  excluded_properties: null,
  property_errors: null
)
```


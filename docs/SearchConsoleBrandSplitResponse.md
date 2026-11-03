# LLMPulse::SearchConsoleBrandSplitResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional] |
| **properties** | [**Array&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional] |
| **excluded_properties** | [**Array&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them | [optional] |
| **property_errors** | [**Array&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures | [optional] |
| **from** | **Date** |  | [optional] |
| **to** | **Date** |  | [optional] |
| **data_through** | **Date** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional] |
| **brand_terms** | **Array&lt;String&gt;** | The project&#39;s brand name, matching names, app names and domain, lowercased, each matched as a whole word | [optional] |
| **totals** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional] |
| **branded** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional] |
| **non_branded** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  | [optional] |
| **unclassified** | [**SearchConsoleBrandSplitResponseUnclassified**](SearchConsoleBrandSplitResponseUnclassified.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleBrandSplitResponse.new(
  project_id: null,
  property: null,
  properties: null,
  excluded_properties: null,
  property_errors: null,
  from: null,
  to: null,
  data_through: null,
  brand_terms: null,
  totals: null,
  branded: null,
  non_branded: null,
  unclassified: null,
  request_id: null
)
```


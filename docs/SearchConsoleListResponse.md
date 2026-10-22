# LLMPulse::SearchConsoleListResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional] |
| **from** | **Date** |  | [optional] |
| **to** | **Date** |  | [optional] |
| **data_through** | **Date** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** | Rows in this window (one Google request, at most 25,000) | [optional] |
| **sort** | **String** |  | [optional] |
| **start_row** | **Integer** | Present when start_row was set | [optional] |
| **truncated** | **Boolean** | Present (true) when Google returned 25,000 rows, so more rows exist past this window | [optional] |
| **data** | [**Array&lt;SearchConsoleListResponseDataInner&gt;**](SearchConsoleListResponseDataInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |
| **properties** | [**Array&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) | [optional] |
| **excluded_properties** | [**Array&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them | [optional] |
| **property_errors** | [**Array&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleListResponse.new(
  project_id: null,
  property: null,
  from: null,
  to: null,
  data_through: null,
  page: null,
  per_page: null,
  total: null,
  sort: null,
  start_row: null,
  truncated: null,
  data: null,
  request_id: null,
  properties: null,
  excluded_properties: null,
  property_errors: null
)
```


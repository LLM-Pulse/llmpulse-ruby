# LLMPulse::SearchConsoleAiVisibilityGapsResponse

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
| **min_impressions** | **Integer** |  | [optional] |
| **unmatched_only** | **Boolean** |  | [optional] |
| **matched_count** | **Integer** | Queries with at least min_impressions that match a prompt of the project, counted before unmatched_only leaves them out | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** | Rows in the report before paging | [optional] |
| **truncated** | **Boolean** | Present (true) when Google returned its 25,000-row maximum for a property, so the report covers its top rows only | [optional] |
| **data** | [**Array&lt;SearchConsoleAiVisibilityGapsResponseDataInner&gt;**](SearchConsoleAiVisibilityGapsResponseDataInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleAiVisibilityGapsResponse.new(
  project_id: null,
  property: null,
  properties: null,
  excluded_properties: null,
  property_errors: null,
  from: null,
  to: null,
  data_through: null,
  min_impressions: null,
  unmatched_only: null,
  matched_count: null,
  page: null,
  per_page: null,
  total: null,
  truncated: null,
  data: null,
  request_id: null
)
```


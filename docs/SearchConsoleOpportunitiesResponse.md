# LLMPulse::SearchConsoleOpportunitiesResponse

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
| **min_position** | **Float** |  | [optional] |
| **max_position** | **Float** |  | [optional] |
| **top_ctr** | **Float** | CTR (0..1) of the property&#39;s queries averaging position 3 or better in the window; null when there are none, and then no potential_clicks | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** | Rows in the report before paging | [optional] |
| **truncated** | **Boolean** | Present (true) when Google returned its 25,000-row maximum for a property, so the report covers its top rows only | [optional] |
| **data** | [**Array&lt;SearchConsoleOpportunitiesResponseDataInner&gt;**](SearchConsoleOpportunitiesResponseDataInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleOpportunitiesResponse.new(
  project_id: null,
  property: null,
  properties: null,
  excluded_properties: null,
  property_errors: null,
  from: null,
  to: null,
  data_through: null,
  min_impressions: null,
  min_position: null,
  max_position: null,
  top_ctr: null,
  page: null,
  per_page: null,
  total: null,
  truncated: null,
  data: null,
  request_id: null
)
```


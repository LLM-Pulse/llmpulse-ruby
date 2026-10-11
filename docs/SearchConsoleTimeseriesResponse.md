# LLMPulse::SearchConsoleTimeseriesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  | [optional] |
| **from** | **Date** |  | [optional] |
| **to** | **Date** |  | [optional] |
| **data_through** | **Date** | Latest date Google has published for the property (it lags 2-3 days). Later days are missing, not zero. | [optional] |
| **granularity** | **String** |  | [optional] |
| **data** | [**Array&lt;SearchConsoleTimeseriesResponseDataInner&gt;**](SearchConsoleTimeseriesResponseDataInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsoleTimeseriesResponse.new(
  project_id: null,
  property: null,
  from: null,
  to: null,
  data_through: null,
  granularity: null,
  data: null,
  request_id: null
)
```


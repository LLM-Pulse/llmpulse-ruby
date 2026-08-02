# LLMPulse::TimeseriesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **granularity** | **String** |  | [optional] |
| **filters** | **Object** |  | [optional] |
| **series** | **Hash&lt;String, Array&lt;TimeseriesSeries&gt;&gt;** |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TimeseriesResponse.new(
  project_id: null,
  from: null,
  to: null,
  granularity: null,
  filters: null,
  series: null,
  request_id: null
)
```


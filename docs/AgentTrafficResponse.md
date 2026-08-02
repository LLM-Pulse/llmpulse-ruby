# LLMPulse::AgentTrafficResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **from** | **Date** |  | [optional] |
| **to** | **Date** |  | [optional] |
| **group_by** | **String** |  | [optional] |
| **granularity** | **String** |  | [optional] |
| **totals** | **Hash&lt;String, Integer&gt;** |  | [optional] |
| **timeseries** | **Hash&lt;String, Hash&lt;String, Integer&gt;&gt;** |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AgentTrafficResponse.new(
  project_id: null,
  from: null,
  to: null,
  group_by: null,
  granularity: null,
  totals: null,
  timeseries: null,
  request_id: null
)
```


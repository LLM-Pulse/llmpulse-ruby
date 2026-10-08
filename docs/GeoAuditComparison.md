# LLMPulse::GeoAuditComparison

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **from_run** | [**GeoAuditRun**](GeoAuditRun.md) |  | [optional] |
| **to_run** | [**GeoAuditRun**](GeoAuditRun.md) |  | [optional] |
| **comparable** | **Boolean** |  | [optional] |
| **score_delta** | **Float** |  | [optional] |
| **metric_deltas** | **Hash&lt;String, Float&gt;** |  | [optional] |
| **counts** | **Hash&lt;String, Integer&gt;** |  | [optional] |
| **changes** | [**Array&lt;GeoAuditComparisonChangesInner&gt;**](GeoAuditComparisonChangesInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAuditComparison.new(
  project_id: null,
  from_run: null,
  to_run: null,
  comparable: null,
  score_delta: null,
  metric_deltas: null,
  counts: null,
  changes: null,
  request_id: null
)
```


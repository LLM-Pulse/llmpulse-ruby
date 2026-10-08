# LLMPulse::GeoAlert

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **audit_id** | **String** |  | [optional] |
| **audit_type** | **String** |  | [optional] |
| **target** | **String** |  | [optional] |
| **run_sequence** | **Integer** |  | [optional] |
| **severity** | **String** |  | [optional] |
| **events** | [**Array&lt;GeoAlertEventsInner&gt;**](GeoAlertEventsInner.md) |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **app_url** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAlert.new(
  id: null,
  audit_id: null,
  audit_type: null,
  target: null,
  run_sequence: null,
  severity: null,
  events: null,
  created_at: null,
  app_url: null
)
```


# LLMPulse::ListWebhooks200ResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **project_id** | **Integer** |  | [optional] |
| **event_type** | **String** |  | [optional] |
| **target_url** | **String** |  | [optional] |
| **disabled** | **Boolean** |  | [optional] |
| **failure_count** | **Integer** |  | [optional] |
| **last_delivered_at** | **Time** |  | [optional] |
| **created_at** | **Time** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ListWebhooks200ResponseDataInner.new(
  id: null,
  project_id: null,
  event_type: null,
  target_url: null,
  disabled: null,
  failure_count: null,
  last_delivered_at: null,
  created_at: null
)
```


# LLMPulse::CreateWebhookRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **event_type** | **String** |  |  |
| **target_url** | **String** | Public HTTPS URL that will receive signed event payloads |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateWebhookRequest.new(
  project_id: null,
  event_type: null,
  target_url: null
)
```


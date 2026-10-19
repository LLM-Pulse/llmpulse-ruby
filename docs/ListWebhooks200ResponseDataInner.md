# LLMPulse::ListWebhooks200ResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **project_id** | **Integer** |  | [optional] |
| **event_type** | **String** |  | [optional] |
| **target_url** | **String** | The URL deliveries are sent to. A read-only API key receives only its scheme, host and any non-default port followed by &#x60;/…&#x60; (for example &#x60;https://hook.eu1.make.com/…&#x60;); a &#x60;read_write&#x60; scope key receives the full URL. | [optional] |
| **disabled** | **Boolean** | True when the subscription receives no more events, including when the API key or OAuth connection that created it was revoked, or when that API key is limited to some projects and no longer covers the subscription&#39;s project. Creating it again with the same project, event and URL replaces it with a new subscription and secret. | [optional] |
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


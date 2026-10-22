# LLMPulse::ProjectDetailsAllOfAiTraffic

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **provider** | **String** | The connected provider (e.g. google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo, piano), null when not connected | [optional] |
| **connect_url** | **String** | The in-app AI Traffic page, where the provider is connected or reconnected | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetailsAllOfAiTraffic.new(
  status: null,
  provider: null,
  connect_url: null
)
```


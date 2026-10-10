# LLMPulse::WebAnalyticsQueryResponseColumnsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **kind** | **String** | dimension or metric, when the provider says. | [optional] |
| **type** | **String** | The provider&#39;s column type, when it says (PostHog). | [optional] |
| **label** | **String** | The provider&#39;s display label, when it sends one (Piano). | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::WebAnalyticsQueryResponseColumnsInner.new(
  name: null,
  kind: null,
  type: null,
  label: null
)
```


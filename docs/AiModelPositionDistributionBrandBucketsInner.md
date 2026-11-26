# LLMPulse::AiModelPositionDistributionBrandBucketsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key** | **String** |  |  |
| **label** | **String** |  |  |
| **color** | **String** | Hex color the app charts the bucket with |  |
| **total** | **Integer** | Mentions in the bucket over the window |  |
| **data** | [**Array&lt;AiModelPositionDistributionBrandBucketsInnerDataInner&gt;**](AiModelPositionDistributionBrandBucketsInnerDataInner.md) | One point per period of the window, oldest first, 0 included |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiModelPositionDistributionBrandBucketsInner.new(
  key: null,
  label: null,
  color: null,
  total: null,
  data: null
)
```


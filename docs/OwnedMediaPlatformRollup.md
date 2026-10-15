# LLMPulse::OwnedMediaPlatformRollup

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** |  | [optional] |
| **connected** | **Boolean** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **yours** | **Integer** |  | [optional] |
| **share_pct** | **Float** |  | [optional] |
| **weekly** | [**Array&lt;OwnedMediaPlatformRollupWeeklyInner&gt;**](OwnedMediaPlatformRollupWeeklyInner.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaPlatformRollup.new(
  provider: null,
  connected: null,
  total: null,
  yours: null,
  share_pct: null,
  weekly: null
)
```


# LLMPulse::OwnedMediaWeek

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **week** | **Date** | The Monday that starts the week | [optional] |
| **citations** | **Integer** |  | [optional] |
| **yours** | **Integer** | Null for provider&#x3D;overview, whose rollups have no weekly split | [optional] |
| **other** | **Integer** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaWeek.new(
  week: null,
  citations: null,
  yours: null,
  other: null
)
```


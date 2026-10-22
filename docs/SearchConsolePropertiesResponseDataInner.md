# LLMPulse::SearchConsolePropertiesResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Property id, the value the property parameter takes, e.g. sc-domain:example.com | [optional] |
| **name** | **String** |  | [optional] |
| **primary** | **Boolean** | The property read when the property parameter is omitted | [optional] |
| **type** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **last_synced_at** | **Time** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsolePropertiesResponseDataInner.new(
  id: null,
  name: null,
  primary: null,
  type: null,
  status: null,
  last_synced_at: null
)
```


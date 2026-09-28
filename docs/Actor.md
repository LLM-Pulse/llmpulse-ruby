# LLMPulse::Actor

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** |  | [optional] |
| **id** | **Integer** |  | [optional] |
| **competitor_id** | **Integer** |  | [optional] |
| **name** | **String** |  | [optional] |
| **domain** | **String** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::Actor.new(
  type: null,
  id: null,
  competitor_id: null,
  name: null,
  domain: null
)
```


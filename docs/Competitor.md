# LLMPulse::Competitor

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **name** | **String** |  | [optional] |
| **domain** | **String** |  | [optional] |
| **actor_type** | **String** | Only present when include_project_brand&#x3D;true | [optional] |
| **is_own** | **Boolean** | Only present when include_project_brand&#x3D;true | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::Competitor.new(
  id: null,
  name: null,
  domain: null,
  actor_type: null,
  is_own: null
)
```


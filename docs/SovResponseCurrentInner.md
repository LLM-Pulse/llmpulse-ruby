# LLMPulse::SovResponseCurrentInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **actor** | [**Actor**](Actor.md) |  | [optional] |
| **share** | **Float** |  | [optional] |
| **previous_share** | **Float** | The actor&#39;s share in the last complete bucket before the current one; null without complete history. | [optional] |
| **avg_share** | **Float** | Mean share across complete buckets with data (partial buckets excluded); null without complete history. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SovResponseCurrentInner.new(
  actor: null,
  share: null,
  previous_share: null,
  avg_share: null
)
```


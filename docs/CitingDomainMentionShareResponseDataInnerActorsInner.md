# LLMPulse::CitingDomainMentionShareResponseDataInnerActorsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** | brand or competitor |  |
| **id** | **Integer** | Null for the brand, the competitor id otherwise |  |
| **name** | **String** |  |  |
| **mentions** | **Integer** |  |  |
| **share** | **Float** | mentions as a percentage (0-100) of total_mentions |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitingDomainMentionShareResponseDataInnerActorsInner.new(
  type: null,
  id: null,
  name: null,
  mentions: null,
  share: null
)
```


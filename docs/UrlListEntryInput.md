# LLMPulse::UrlListEntryInput

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **value** | **String** | An exact URL, a \&quot;host/path/*\&quot; prefix or a domain. |  |
| **match_type** | **String** |  | [optional] |
| **added_on** | **Date** | When the URL was published or bought. Default today. | [optional] |
| **cost** | **Float** | What the URL cost, in the list currency. | [optional] |
| **channel** | **String** | Where it came from, such as a marketplace or PR agency. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListEntryInput.new(
  value: null,
  match_type: null,
  added_on: null,
  cost: null,
  channel: null
)
```


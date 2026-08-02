# LLMPulse::ProjectCreateResponseCompetitors

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **created** | **Integer** |  | [optional] |
| **processing** | **Boolean** | Always false; competitors are ready when the project transaction commits. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectCreateResponseCompetitors.new(
  created: null,
  processing: false
)
```


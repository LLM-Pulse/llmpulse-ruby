# LLMPulse::CitingDomainMentionShareResponseDataInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |
| **responses_citing** | **Integer** | Answers citing the domain |  |
| **total_mentions** | **Integer** | Brand and competitor mentions in those answers, each answer counted once per brand |  |
| **actors** | [**Array&lt;CitingDomainMentionShareResponseDataInnerActorsInner&gt;**](CitingDomainMentionShareResponseDataInnerActorsInner.md) | The brand and every competitor, most mentions first; empty when no answer cites the domain |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitingDomainMentionShareResponseDataInner.new(
  domain: null,
  responses_citing: null,
  total_mentions: null,
  actors: null
)
```


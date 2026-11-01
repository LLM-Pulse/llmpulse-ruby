# LLMPulse::ApiErrorError

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **code** | **String** |  | [optional] |
| **message** | **String** |  | [optional] |
| **meta** | **Object** | Extra detail for some codes. A not-connected or access-revoked error from the Search Console, AI traffic, web analytics or agent traffic endpoints carries connect_url, the in-app page where the user connects or reconnects the source. A prompt write refused because a launched pitch project&#39;s prompts are fixed carries reason pitch_prompts_frozen. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ApiErrorError.new(
  code: null,
  message: null,
  meta: null
)
```


# LLMPulse::PromptGenerationResponseError

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **code** | **String** | ERR_GENERATION_FAILED, ERR_NOT_FOUND (no suggestions came back), ERR_QUOTA_EXCEEDED, or a Search Console error code |  |
| **message** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptGenerationResponseError.new(
  code: null,
  message: null
)
```


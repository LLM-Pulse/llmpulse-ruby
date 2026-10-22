# LLMPulse::SearchConsolePropertyError

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **code** | **String** |  | [optional] |
| **message** | **String** |  | [optional] |
| **retry_after** | **Integer** | Seconds to wait before retrying, for ERR_SEARCH_CONSOLE_UPSTREAM | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SearchConsolePropertyError.new(
  id: null,
  name: null,
  code: null,
  message: null,
  retry_after: null
)
```


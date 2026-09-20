# LLMPulse::AccountQuota

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **limit** | **Integer** |  | [optional] |
| **used** | **Integer** |  | [optional] |
| **remaining** | **Integer** |  | [optional] |
| **unlimited** | **Boolean** |  | [optional] |
| **period** | **String** | Reset window for quotas that reset (e.g. month) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AccountQuota.new(
  limit: null,
  used: null,
  remaining: null,
  unlimited: null,
  period: null
)
```


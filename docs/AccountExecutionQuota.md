# LLMPulse::AccountExecutionQuota

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **limit** | **Integer** |  | [optional] |
| **used** | **Integer** |  | [optional] |
| **remaining** | **Integer** |  | [optional] |
| **unlimited** | **Boolean** |  | [optional] |
| **period** | **String** | The tracking window, from the account&#39;s tracking cadence (week runs Monday to Sunday) | [optional] |
| **resets_at** | **Time** | When the next window starts and the allowance is full again (00:00 Europe/Madrid) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AccountExecutionQuota.new(
  limit: null,
  used: null,
  remaining: null,
  unlimited: null,
  period: null,
  resets_at: null
)
```


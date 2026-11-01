# LLMPulse::AccountPitchQuota

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **limit** | **Integer** |  | [optional] |
| **used** | **Integer** |  | [optional] |
| **remaining** | **Integer** |  | [optional] |
| **unlimited** | **Boolean** |  | [optional] |
| **period** | **String** | Always month | [optional] |
| **resets_on** | **Date** | The first day of next month, when the allowance starts again | [optional] |
| **access** | **String** | Whether the account may create pitch projects. The account owner or an account admin (co-owner) requests access in Account Settings &gt; Pitch projects and our team reviews it; approved access goes dormant while the account is below the Scale tier, on a trial, has a payment problem, is set to cancel or has an allowance of 0 | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AccountPitchQuota.new(
  limit: null,
  used: null,
  remaining: null,
  unlimited: null,
  period: null,
  resets_on: null,
  access: null
)
```


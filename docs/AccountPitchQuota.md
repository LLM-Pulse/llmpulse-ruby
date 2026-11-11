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
| **access** | **String** | Whether the account may create pitch projects, which are for agency and platform accounts (the account type, which the account owner or an account admin changes in Account Settings &gt; Profile). none means the account is not an agency; approved access goes dormant while the account is below the Scale tier, on a trial, has a payment problem, is set to cancel or has an allowance of 0; revoked means our team turned it off. pending and rejected are no longer returned | [optional] |

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


# LLMPulse::ApiKeyInfo

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **name** | **String** |  |  |
| **prefix** | **String** | The visible start of the token, to recognize the key. Never the secret itself. |  |
| **scope** | **String** |  |  |
| **project_scoped** | **Boolean** | True when the key is limited to project_ids; false for an account-wide key. |  |
| **project_ids** | **Array&lt;Integer&gt;** | The projects the key is limited to; empty for an account-wide key. |  |
| **created_at** | **Time** |  |  |
| **last_used_at** | **Time** | Updated at most once a minute. |  |
| **revoked_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ApiKeyInfo.new(
  id: null,
  name: null,
  prefix: null,
  scope: null,
  project_scoped: null,
  project_ids: null,
  created_at: null,
  last_used_at: null,
  revoked_at: null
)
```


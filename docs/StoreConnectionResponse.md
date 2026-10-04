# LLMPulse::StoreConnectionResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform** | **String** | The store platform, e.g. shopify |  |
| **domain** | **String** | The store domain as compared: lowercase, without scheme, www or path |  |
| **project** | [**StoreConnectionResponseProject**](StoreConnectionResponseProject.md) |  |  |
| **ambiguous** | **Boolean** | True when several live projects match the store domain (for example one project per market). project is then null and the app asks the key holder to pick from candidates. |  |
| **candidates** | [**Array&lt;StoreConnectionResponseCandidatesInner&gt;**](StoreConnectionResponseCandidatesInner.md) | Every live project of the account, for a project picker |  |
| **account** | [**StoreConnectionResponseAccount**](StoreConnectionResponseAccount.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::StoreConnectionResponse.new(
  platform: null,
  domain: null,
  project: null,
  ambiguous: null,
  candidates: null,
  account: null,
  request_id: null
)
```


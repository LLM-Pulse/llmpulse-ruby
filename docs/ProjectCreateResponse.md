# LLMPulse::ProjectCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project** | **Object** | Same shape as GET /dimensions/projects/{id} | [optional] |
| **prompts** | [**ProjectCreateResponsePrompts**](ProjectCreateResponsePrompts.md) |  | [optional] |
| **competitors** | [**ProjectCreateResponseCompetitors**](ProjectCreateResponseCompetitors.md) |  | [optional] |
| **collections** | [**Array&lt;ProjectCreateResponseCollectionsInner&gt;**](ProjectCreateResponseCollectionsInner.md) | Collections created from the request&#39;s collections field (empty when none were sent; absent on an idempotent replay) | [optional] |
| **same_domain_projects** | [**Array&lt;ProjectCreateResponseSameDomainProjectsInner&gt;**](ProjectCreateResponseSameDomainProjectsInner.md) | Projects the caller can already see on the same domain (absent on an idempotent replay). Informational only: the create is never blocked, since one domain tracked per market is a normal setup. | [optional] |
| **email_subscription** | [**ProjectCreateResponseEmailSubscription**](ProjectCreateResponseEmailSubscription.md) |  | [optional] |
| **limits** | [**ProjectCreateResponseLimits**](ProjectCreateResponseLimits.md) |  | [optional] |
| **idempotent** | **Boolean** | Present and true only on external_identifier replays | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectCreateResponse.new(
  project: null,
  prompts: null,
  competitors: null,
  collections: null,
  same_domain_projects: null,
  email_subscription: null,
  limits: null,
  idempotent: null,
  request_id: null
)
```


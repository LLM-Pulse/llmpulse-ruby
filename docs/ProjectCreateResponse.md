# LLMPulse::ProjectCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project** | **Object** | Same shape as GET /dimensions/projects/{id} | [optional] |
| **prompts** | [**ProjectCreateResponsePrompts**](ProjectCreateResponsePrompts.md) |  | [optional] |
| **competitors** | [**ProjectCreateResponseCompetitors**](ProjectCreateResponseCompetitors.md) |  | [optional] |
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
  email_subscription: null,
  limits: null,
  idempotent: null,
  request_id: null
)
```


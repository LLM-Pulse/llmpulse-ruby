# LLMPulse::PromptsCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **created** | **Integer** |  | [optional] |
| **skipped** | **Integer** |  | [optional] |
| **total_after** | **Integer** |  | [optional] |
| **prompts_available** | **Integer** |  | [optional] |
| **tracked** | **Boolean** | Whether scheduled runs include the project the prompts were added to. False when it is paused or beyond the plan&#39;s project limit, so the new prompts do not run until that changes | [optional] |
| **untracked_reason** | **String** | Why tracked is false: paused or project_limit. Null when tracked | [optional] |
| **warning** | **String** | What to do when tracked is false. Null when tracked | [optional] |
| **data** | [**Array&lt;PromptsCreateResponseDataInner&gt;**](PromptsCreateResponseDataInner.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptsCreateResponse.new(
  project_id: null,
  created: null,
  skipped: null,
  total_after: null,
  prompts_available: null,
  tracked: null,
  untracked_reason: null,
  warning: null,
  data: null,
  request_id: null
)
```


# LLMPulse::PromptTagsAssignResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **prompts_targeted** | **Integer** | Prompts of the project among prompt_ids |  |
| **tags_attached** | [**Array&lt;TagRef&gt;**](TagRef.md) |  |  |
| **new_links_created** | **Integer** |  |  |
| **skipped_already_linked** | **Integer** |  |  |
| **missing_tag_names** | **Array&lt;String&gt;** | tag_names that matched no tag and were not created |  |
| **ignored_prompt_ids** | **Array&lt;Integer&gt;** | prompt_ids that are not prompts of this project |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptTagsAssignResponse.new(
  project_id: null,
  prompts_targeted: null,
  tags_attached: null,
  new_links_created: null,
  skipped_already_linked: null,
  missing_tag_names: null,
  ignored_prompt_ids: null,
  request_id: null
)
```


# LLMPulse::PromptTagsRemoveResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **prompts_targeted** | **Integer** | Prompts of the project among prompt_ids |  |
| **tags_detached** | [**Array&lt;TagRef&gt;**](TagRef.md) |  |  |
| **links_removed** | **Integer** |  |  |
| **skipped_not_linked** | **Integer** |  |  |
| **missing_tag_names** | **Array&lt;String&gt;** | tag_names that matched no tag |  |
| **ignored_prompt_ids** | **Array&lt;Integer&gt;** | prompt_ids that are not prompts of this project |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptTagsRemoveResponse.new(
  project_id: null,
  prompts_targeted: null,
  tags_detached: null,
  links_removed: null,
  skipped_not_linked: null,
  missing_tag_names: null,
  ignored_prompt_ids: null,
  request_id: null
)
```


# LLMPulse::AssignPromptTagsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **prompt_ids** | **Array&lt;Integer&gt;** |  |  |
| **tag_ids** | **Array&lt;Integer&gt;** |  | [optional] |
| **tag_names** | **Array&lt;String&gt;** |  | [optional] |
| **create_missing** | **Boolean** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AssignPromptTagsRequest.new(
  project_id: null,
  prompt_ids: null,
  tag_ids: null,
  tag_names: null,
  create_missing: null
)
```


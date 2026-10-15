# LLMPulse::SuggestedPromptsAcceptRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **ids** | **Array&lt;Integer&gt;** | Suggestion ids to accept (max 100) |  |
| **tag_ids** | **Array&lt;Integer&gt;** | One tag id to put the new prompts in | [optional] |
| **tag_names** | **Array&lt;String&gt;** | One tag name (case-insensitive) to put the new prompts in | [optional] |
| **create_missing** | **Boolean** | Create the tag named in tag_names when it does not exist | [optional][default to false] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SuggestedPromptsAcceptRequest.new(
  project_id: null,
  ids: null,
  tag_ids: null,
  tag_names: null,
  create_missing: null
)
```


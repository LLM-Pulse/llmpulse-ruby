# LLMPulse::CreateCollectionRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **prompt_ids** | **Array&lt;Integer&gt;** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateCollectionRequest.new(
  project_id: null,
  name: null,
  description: null,
  prompt_ids: null
)
```


# LLMPulse::CollectionCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **collection** | [**CollectionCreateResponseCollection**](CollectionCreateResponseCollection.md) |  |  |
| **prompts_attached** | **Integer** | Existing prompts attached through prompt_ids |  |
| **total_collections** | **Integer** |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CollectionCreateResponse.new(
  project_id: null,
  collection: null,
  prompts_attached: null,
  total_collections: null,
  request_id: null
)
```


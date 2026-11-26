# LLMPulse::CollectionDeleteResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **deleted** | **Boolean** | Always true |  |
| **id** | **Integer** |  |  |
| **name** | **String** |  |  |
| **prompts_kept** | **Integer** | Prompts the collection held; they stay in the project |  |
| **total_collections** | **Integer** | Collections left in the project |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CollectionDeleteResponse.new(
  project_id: null,
  deleted: null,
  id: null,
  name: null,
  prompts_kept: null,
  total_collections: null,
  request_id: null
)
```


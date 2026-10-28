# LLMPulse::ProjectDeleteResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **deleted** | **Boolean** | Always true |  |
| **name** | **String** | The deleted project&#39;s name |  |
| **url** | **String** | The deleted project&#39;s website |  |
| **note** | **String** | What happens next; the deletion cannot be undone |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDeleteResponse.new(
  project_id: null,
  deleted: null,
  name: null,
  url: null,
  note: null,
  request_id: null
)
```


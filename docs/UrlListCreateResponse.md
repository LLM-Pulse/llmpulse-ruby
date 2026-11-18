# LLMPulse::UrlListCreateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **url_list** | [**UrlListWithCounts**](UrlListWithCounts.md) |  |  |
| **entries_added** | **Integer** |  |  |
| **invalid_entries** | [**Array&lt;UrlListInvalidEntry&gt;**](UrlListInvalidEntry.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListCreateResponse.new(
  project_id: null,
  url_list: null,
  entries_added: null,
  invalid_entries: null,
  request_id: null
)
```


# LLMPulse::UrlListEntriesAddResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **url_list_id** | **Integer** |  |  |
| **added** | **Integer** |  |  |
| **updated** | **Integer** |  |  |
| **invalid_entries** | [**Array&lt;UrlListInvalidEntry&gt;**](UrlListInvalidEntry.md) |  |  |
| **entries_count** | **Integer** |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListEntriesAddResponse.new(
  project_id: null,
  url_list_id: null,
  added: null,
  updated: null,
  invalid_entries: null,
  entries_count: null,
  request_id: null
)
```


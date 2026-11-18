# LLMPulse::UrlListEntriesAddRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **entries** | [**Array&lt;UrlListEntryInput&gt;**](UrlListEntryInput.md) |  |  |
| **match_type** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListEntriesAddRequest.new(
  project_id: null,
  entries: null,
  match_type: null
)
```


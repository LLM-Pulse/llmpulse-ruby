# LLMPulse::UrlListCreateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **currency** | **String** |  | [optional][default to &#39;USD&#39;] |
| **entries** | [**Array&lt;UrlListEntryInput&gt;**](UrlListEntryInput.md) |  | [optional] |
| **match_type** | **String** | Read every entry without its own match_type as this type. Default detects it from each value. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListCreateRequest.new(
  project_id: null,
  name: null,
  description: null,
  currency: null,
  entries: null,
  match_type: null
)
```


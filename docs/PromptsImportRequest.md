# LLMPulse::PromptsImportRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **rows** | [**Array&lt;PromptsImportRequestRowsInner&gt;**](PromptsImportRequestRowsInner.md) | One object per prompt (max 500) |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptsImportRequest.new(
  project_id: null,
  rows: null
)
```


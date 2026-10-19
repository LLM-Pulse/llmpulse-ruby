# LLMPulse::PromptsImportResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **processed_rows** | **Integer** | Distinct rows imported or matched to an existing prompt |  |
| **created** | **Integer** |  |  |
| **duplicates** | **Integer** | Rows that matched an existing prompt (they still get the row&#39;s tags, unless a team member lacks update access to Prompts) |  |
| **tagged** | **Integer** | New prompt-tag links |  |
| **created_tags** | **Integer** |  |  |
| **row_errors** | [**Array&lt;PromptsImportResponseRowErrorsInner&gt;**](PromptsImportResponseRowErrorsInner.md) | Rows that were skipped or whose tags were not added, by their index in rows |  |
| **length_warning** | **String** | Which tracked AI models will skip new prompts that are too long for them |  |
| **prompts_available** | **Integer** | Prompt slots left on the plan; null when unlimited |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptsImportResponse.new(
  project_id: null,
  processed_rows: null,
  created: null,
  duplicates: null,
  tagged: null,
  created_tags: null,
  row_errors: null,
  length_warning: null,
  prompts_available: null,
  request_id: null
)
```


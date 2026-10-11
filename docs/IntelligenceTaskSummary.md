# LLMPulse::IntelligenceTaskSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **public_id** | **String** |  |  |
| **task_type** | **String** |  |  |
| **title** | **String** |  |  |
| **status** | **String** |  |  |
| **prompt_id** | **Integer** |  |  |
| **prompt_text** | **String** |  |  |
| **word_count** | **Integer** |  |  |
| **manually_edited_at** | **Time** | When the content was last edited by hand; null while the output is as generated |  |
| **created_at** | **Time** |  |  |
| **processed_at** | **Time** |  |  |
| **result_version** | **String** | Concurrency token for content edits: send it back as result_version on PATCH /intelligence_tasks/{id} so an edit composed before a regeneration is refused with ERR_STALE_CONTENT (409). It is \&quot;0\&quot; until the task first completes, then changes each time a generation or regeneration replaces result_data, never on a manual edit or a revert. Treat it as opaque text |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::IntelligenceTaskSummary.new(
  id: null,
  public_id: null,
  task_type: null,
  title: null,
  status: null,
  prompt_id: null,
  prompt_text: null,
  word_count: null,
  manually_edited_at: null,
  created_at: null,
  processed_at: null,
  result_version: 1775642580
)
```


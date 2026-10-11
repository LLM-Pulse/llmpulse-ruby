# LLMPulse::IntelligenceTaskUpdateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **edits** | **Hash&lt;String, String&gt;** | Dotted result_data paths (title, sections.0.content, key_points.2) mapped to their replacement text. Only string fields that already exist are editable; sections cannot be added or removed. |  |
| **result_version** | **String** | Optional. The result_version of the task as last read. When sent, the edit is refused with ERR_STALE_CONTENT (409) and nothing is written if the task was regenerated since. Omitted, null or empty, the edits apply to whatever the task holds now | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::IntelligenceTaskUpdateRequest.new(
  project_id: null,
  edits: {&quot;title&quot;:&quot;How to measure AI visibility in 2026&quot;,&quot;sections.0.content&quot;:&quot;AI visibility is the share of AI answers that mention your brand.&quot;},
  result_version: 1775642580
)
```


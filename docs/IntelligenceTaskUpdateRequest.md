# LLMPulse::IntelligenceTaskUpdateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **edits** | **Hash&lt;String, String&gt;** | Dotted result_data paths (title, sections.0.content, key_points.2) mapped to their replacement text. Only string fields that already exist are editable; sections cannot be added or removed. |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::IntelligenceTaskUpdateRequest.new(
  project_id: null,
  edits: {&quot;title&quot;:&quot;How to measure AI visibility in 2026&quot;,&quot;sections.0.content&quot;:&quot;AI visibility is the share of AI answers that mention your brand.&quot;}
)
```


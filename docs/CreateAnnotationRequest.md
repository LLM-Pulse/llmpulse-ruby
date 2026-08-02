# LLMPulse::CreateAnnotationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **title** | **String** |  |  |
| **annotation_date** | **Date** | ISO YYYY-MM-DD; defaults to today | [optional] |
| **description** | **String** |  | [optional] |
| **color** | **String** | Hex color, e.g. #2563eb | [optional] |
| **annotation_category_id** | **Integer** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateAnnotationRequest.new(
  project_id: null,
  title: null,
  annotation_date: null,
  description: null,
  color: null,
  annotation_category_id: null
)
```


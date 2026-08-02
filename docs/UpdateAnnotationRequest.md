# LLMPulse::UpdateAnnotationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **title** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **annotation_date** | **Date** |  | [optional] |
| **color** | **String** |  | [optional] |
| **annotation_category_id** | **Integer** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UpdateAnnotationRequest.new(
  project_id: null,
  title: null,
  description: null,
  annotation_date: null,
  color: null,
  annotation_category_id: null
)
```


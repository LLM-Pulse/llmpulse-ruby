# LLMPulse::AnnotationRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **title** | **String** |  |  |
| **description** | **String** |  |  |
| **annotation_date** | **Date** |  |  |
| **color** | **String** |  |  |
| **category** | **String** | user (written by a person) or system (added by the platform) |  |
| **origin** | **String** | manual, platform (a platform-wide event) or automation (a project change recorded automatically) |  |
| **annotation_category** | [**AnnotationRecordAnnotationCategory**](AnnotationRecordAnnotationCategory.md) |  |  |
| **editable** | **Boolean** | Whether the requesting user may update or delete it |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AnnotationRecord.new(
  id: null,
  title: null,
  description: null,
  annotation_date: null,
  color: null,
  category: null,
  origin: null,
  annotation_category: null,
  editable: null,
  created_at: null
)
```


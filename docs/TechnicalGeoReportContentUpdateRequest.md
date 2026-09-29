# LLMPulse::TechnicalGeoReportContentUpdateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **report_type** | **String** | Only llms_txt reports have editable content |  |
| **content_version** | **String** | result_data.content_version of the report as last read. It changes on every save; a value that no longer matches is refused as stale |  |
| **edits** | [**TechnicalGeoReportContentUpdateRequestEdits**](TechnicalGeoReportContentUpdateRequestEdits.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::TechnicalGeoReportContentUpdateRequest.new(
  project_id: null,
  report_type: null,
  content_version: 1790683200123456,
  edits: null
)
```


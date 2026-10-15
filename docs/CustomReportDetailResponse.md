# LLMPulse::CustomReportDetailResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **id** | **Integer** |  |  |
| **name** | **String** |  |  |
| **date_range** | [**CustomReportDateRange**](CustomReportDateRange.md) |  |  |
| **schedule** | [**CustomReportSchedule**](CustomReportSchedule.md) |  |  |
| **recipients_count** | **Integer** |  | [optional] |
| **published** | **Boolean** |  | [optional] |
| **public_link_active** | **Boolean** |  | [optional] |
| **password_protected** | **Boolean** |  | [optional] |
| **portal_only** | **Boolean** |  | [optional] |
| **last_sent_at** | **Time** | When the report was last emailed, on its schedule or with Send now | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |
| **filters** | [**CustomReportFilters**](CustomReportFilters.md) |  |  |
| **compare_previous** | **Boolean** |  | [optional] |
| **attach_excel** | **Boolean** |  | [optional] |
| **manual_send_available_at** | **Time** | When the 10-minute cooldown after the last manual send ends; null when none is running | [optional] |
| **generated_at** | **Time** |  |  |
| **blocks** | [**Array&lt;CustomReportBlock&gt;**](CustomReportBlock.md) | The report layout in order |  |
| **widgets** | [**Array&lt;CustomReportWidget&gt;**](CustomReportWidget.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CustomReportDetailResponse.new(
  project_id: null,
  id: null,
  name: null,
  date_range: null,
  schedule: null,
  recipients_count: null,
  published: null,
  public_link_active: null,
  password_protected: null,
  portal_only: null,
  last_sent_at: null,
  created_at: null,
  updated_at: null,
  filters: null,
  compare_previous: null,
  attach_excel: null,
  manual_send_available_at: null,
  generated_at: null,
  blocks: null,
  widgets: null,
  request_id: null
)
```


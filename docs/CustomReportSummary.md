# LLMPulse::CustomReportSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **name** | **String** |  |  |
| **date_range** | [**CustomReportDateRange**](CustomReportDateRange.md) |  |  |
| **schedule** | [**CustomReportSchedule**](CustomReportSchedule.md) |  |  |
| **recipients_count** | **Integer** |  |  |
| **published** | **Boolean** | Whether the shared link is published |  |
| **public_link_active** | **Boolean** | Whether the shared link opens (published, not made inside a client portal, and the account is active on the Scale tier or higher) |  |
| **password_protected** | **Boolean** |  |  |
| **portal_only** | **Boolean** | Made inside a client portal, so it cannot be shared or emailed |  |
| **widget_count** | **Integer** |  |  |
| **widgets** | [**Array&lt;CustomReportWidgetRef&gt;**](CustomReportWidgetRef.md) |  |  |
| **last_sent_at** | **Time** | When the report was last emailed, on its schedule or with Send now | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CustomReportSummary.new(
  id: null,
  name: null,
  date_range: null,
  schedule: null,
  recipients_count: null,
  published: null,
  public_link_active: null,
  password_protected: null,
  portal_only: null,
  widget_count: null,
  widgets: null,
  last_sent_at: null,
  created_at: null,
  updated_at: null
)
```


# LLMPulse::CustomReportDateRange

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** | rolling (the last range_days days) or previous_month (the previous calendar month) |  |
| **range_days** | **Integer** | Length of a rolling window; null for previous_month |  |
| **from** | **Date** | First day of the window as of now (detail only) | [optional] |
| **to** | **Date** | Last day of the window as of now (detail only) | [optional] |
| **label** | **String** | The window as the report shows it (detail only) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CustomReportDateRange.new(
  type: null,
  range_days: null,
  from: null,
  to: null,
  label: null
)
```


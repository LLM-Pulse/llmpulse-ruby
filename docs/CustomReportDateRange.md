# LLMPulse::CustomReportDateRange

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **type** | **String** | rolling (the last range_days days), previous_month (the previous calendar month), previous_3_months (the 3 calendar months before the current one) or custom (fixed dates, custom_from to custom_to) |  |
| **range_days** | **Integer** | Length of a rolling window; null for the other types |  |
| **custom_from** | **Date** | First day chosen for a custom range; null for the other types |  |
| **custom_to** | **Date** | Last day chosen for a custom range, which can be after today; null for the other types |  |
| **from** | **Date** | First day of the window as of now (detail only) | [optional] |
| **to** | **Date** | Last day of the window as of now (detail only); a custom range stops at today | [optional] |
| **label** | **String** | The window as the report shows it (detail only) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CustomReportDateRange.new(
  type: null,
  range_days: null,
  custom_from: null,
  custom_to: null,
  from: null,
  to: null,
  label: null
)
```


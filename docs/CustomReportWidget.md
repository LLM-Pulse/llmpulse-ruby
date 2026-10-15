# LLMPulse::CustomReportWidget

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **key** | **String** |  |  |
| **label** | **String** |  |  |
| **kind** | **String** |  |  |
| **width** | **String** |  |  |
| **available** | **Boolean** | false when the widget&#39;s data source (web analytics, agent analytics, owned media) is not connected |  |
| **data** | **Hash&lt;String, Object&gt;** | Shaped by kind. timeseries: series [{ name, color, points [{ date, value }] }]. donut: slices [{ name, value, color }]. bar: bars [{ label, value, color }]. kpi_grid: values and changes (null unless the report compares with the previous period). table: rows, one object per row. Null when the widget is not available. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CustomReportWidget.new(
  key: null,
  label: null,
  kind: null,
  width: null,
  available: null,
  data: null
)
```


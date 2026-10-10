# LLMPulse::WebAnalyticsQueryResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **provider** | **String** |  | [optional] |
| **property** | **String** |  | [optional] |
| **columns** | [**Array&lt;WebAnalyticsQueryResponseColumnsInner&gt;**](WebAnalyticsQueryResponseColumnsInner.md) |  | [optional] |
| **rows** | **Array&lt;Array&lt;Object&gt;&gt;** | One array per row, values in column order: strings, numbers or null. | [optional] |
| **row_count** | **Integer** | Rows in this response (at most 5,000). | [optional] |
| **total_rows** | **Integer** | Rows the provider has for the query, when it reports it. | [optional] |
| **truncated** | **Boolean** | True when the provider has more rows than returned; page with its own offset or page field. | [optional] |
| **totals** | **Hash&lt;String, Object&gt;** | Metric totals by metric name, when the query asked for them. | [optional] |
| **notes** | **Array&lt;String&gt;** | Provider caveats: sampling, thresholds, more rows available. | [optional] |
| **meta** | **Hash&lt;String, Object&gt;** | Provider metadata such as GA4 time zone, currency and remaining property quota. | [optional] |
| **fetched_at** | **Time** | When the provider answered. | [optional] |
| **cached** | **Boolean** | True when the answer came from the 10-minute cache instead of the provider. | [optional] |
| **query** | **Hash&lt;String, Object&gt;** | The request as sent to the provider, with the connected property forced and limits applied. | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::WebAnalyticsQueryResponse.new(
  project_id: null,
  provider: null,
  property: null,
  columns: null,
  rows: null,
  row_count: null,
  total_rows: null,
  truncated: null,
  totals: null,
  notes: null,
  meta: null,
  fetched_at: null,
  cached: null,
  query: null,
  request_id: null
)
```


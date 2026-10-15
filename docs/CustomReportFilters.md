# LLMPulse::CustomReportFilters

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **models** | **Array&lt;String&gt;** | AI models the report covers; empty means every enabled model |  |
| **collection_ids** | **Array&lt;Integer&gt;** | Tags the report is limited to; empty means every prompt |  |
| **brand_kind** | **String** |  | [optional] |
| **competitor_ids** | **Array&lt;Integer&gt;** | Competitors compared, the report&#39;s own choice or else the Overview selection |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CustomReportFilters.new(
  models: null,
  collection_ids: null,
  brand_kind: null,
  competitor_ids: null
)
```


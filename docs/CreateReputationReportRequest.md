# LLMPulse::CreateReputationReportRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **recalculate** | **Boolean** | Use this month&#39;s one manual recalculation instead of returning the existing report | [optional][default to false] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateReputationReportRequest.new(
  project_id: null,
  recalculate: null
)
```


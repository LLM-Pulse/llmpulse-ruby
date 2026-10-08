# LLMPulse::GeoAuditIssueList

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **data** | [**Array&lt;GeoAuditIssue&gt;**](GeoAuditIssue.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAuditIssueList.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  data: null,
  request_id: null
)
```


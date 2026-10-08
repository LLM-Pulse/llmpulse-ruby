# LLMPulse::GeoAuditIssueUpdateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **accepted** | **Boolean** | true accepts the issue (it stays listed but leaves the open count until its evidence changes); false reopens it |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAuditIssueUpdateRequest.new(
  project_id: null,
  accepted: null
)
```


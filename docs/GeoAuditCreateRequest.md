# LLMPulse::GeoAuditCreateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **target** | **String** | The domain (site-wide types) or page URL to audit |  |
| **audit_types** | **Array&lt;String&gt;** | One or more audit types; each becomes its own audit and starts its first run |  |
| **cadence** | **String** | once (default), weekly or monthly. Weekly and monthly need a type whose checks are tracked and count against the plan limit of recurring audits | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::GeoAuditCreateRequest.new(
  project_id: null,
  target: null,
  audit_types: null,
  cadence: null
)
```


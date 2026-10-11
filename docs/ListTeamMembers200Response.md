# LLMPulse::ListTeamMembers200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **data** | [**Array&lt;TeamMember&gt;**](TeamMember.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ListTeamMembers200Response.new(
  page: null,
  per_page: null,
  total: null,
  data: null,
  request_id: null
)
```


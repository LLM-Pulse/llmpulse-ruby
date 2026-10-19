# LLMPulse::ProjectCreateRequestCompetitorsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain** | **String** |  |  |
| **brand_name** | **String** |  | [optional] |
| **matching_names** | **Array&lt;String&gt;** | Names this competitor is matched by. At most 50 names of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) and nothing is created | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectCreateRequestCompetitorsInner.new(
  domain: null,
  brand_name: null,
  matching_names: null
)
```


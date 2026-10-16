# LLMPulse::ProjectUpdateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project** | [**ProjectProfile**](ProjectProfile.md) |  |  |
| **updated_fields** | **Array&lt;String&gt;** | The fields the request sent |  |
| **rematching** | **Boolean** | True when a matching_names or additional_owned_domains change started a background recalculation of past answers; further edits are rejected until it finishes |  |
| **note** | **String** | What the change does to mention detection, citation ownership, historical numbers and the prompts the project can hold |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectUpdateResponse.new(
  project: null,
  updated_fields: null,
  rematching: null,
  note: null,
  request_id: null
)
```


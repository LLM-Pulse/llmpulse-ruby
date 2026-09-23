# LLMPulse::CreateTechnicalGeoReportsRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **url** | **String** |  |  |
| **country_code** | **String** | Defaults to the project country | [optional] |
| **output_language_code** | **String** | ISO 639-1 code of the language the llms.txt files are written in (for example es). Defaults to the project language, else en. Only the llms.txt report of the bundle uses it; an unsupported code returns 422 ERR_INVALID_PARAM | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateTechnicalGeoReportsRequest.new(
  project_id: null,
  url: null,
  country_code: null,
  output_language_code: null
)
```


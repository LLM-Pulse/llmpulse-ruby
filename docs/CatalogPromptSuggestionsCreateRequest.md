# LLMPulse::CatalogPromptSuggestionsCreateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **platform** | **String** |  |  |
| **country_code** | **String** | Defaults to the project country | [optional] |
| **language_code** | **String** | Defaults to the project language | [optional] |
| **products** | [**Array&lt;CatalogProduct&gt;**](CatalogProduct.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CatalogPromptSuggestionsCreateRequest.new(
  project_id: null,
  platform: null,
  country_code: null,
  language_code: null,
  products: null
)
```


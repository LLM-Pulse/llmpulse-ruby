# LLMPulse::PromptGenerationResponseParams

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **country_code** | **String** |  | [optional] |
| **language_code** | **String** |  | [optional] |
| **query** | **String** |  | [optional] |
| **count** | **Integer** |  | [optional] |
| **competitor_id** | **Integer** |  | [optional] |
| **search_type** | **String** |  | [optional] |
| **keywords** | **Array&lt;String&gt;** |  | [optional] |
| **source_country_code** | **String** |  | [optional] |
| **source_language_code** | **String** |  | [optional] |
| **min_words** | **Integer** |  | [optional] |
| **all_countries** | **Boolean** |  | [optional] |
| **property** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptGenerationResponseParams.new(
  country_code: null,
  language_code: null,
  query: null,
  count: null,
  competitor_id: null,
  search_type: null,
  keywords: null,
  source_country_code: null,
  source_language_code: null,
  min_words: null,
  all_countries: null,
  property: null
)
```


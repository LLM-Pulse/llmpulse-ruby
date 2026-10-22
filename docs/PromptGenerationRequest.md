# LLMPulse::PromptGenerationRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **source** | **String** | Which Add prompts generator to run |  |
| **query** | **String** | keyword: optional keyword or research query. topic and reddit: required topic (reddit: the brand when search_type&#x3D;brand). paa: one keyword, as an alternative to keywords. | [optional] |
| **count** | **Integer** | keyword and topic: how many suggestions to ask for, capped by the prompt slots left | [optional][default to 20] |
| **country_code** | **String** | ISO 3166-1 alpha-2 country of the suggestions (default the project country) | [optional] |
| **language_code** | **String** | ISO language code of the suggestions (default the project language) | [optional] |
| **competitor_id** | **Integer** | keyword: write the suggestions around this competitor of the project | [optional] |
| **search_type** | **String** | reddit: search discussions of a topic or a brand | [optional][default to &#39;topic&#39;] |
| **keywords** | **Array&lt;String&gt;** | paa: up to 5 keywords; each is a People Also Ask lookup counted against the account&#39;s 24-hour allowance | [optional] |
| **source_country_code** | **String** | translate: country of the prompts to translate | [optional] |
| **source_language_code** | **String** | translate: language of the prompts to translate | [optional] |
| **min_words** | **Integer** | search_console: skip queries shorter than this many words | [optional][default to 0] |
| **all_countries** | **Boolean** | search_console: include queries from every country instead of country_code only | [optional][default to false] |
| **property** | **String** | search_console: the property id to read queries from (GET /search_console/properties lists them); the primary property when omitted | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptGenerationRequest.new(
  project_id: null,
  source: null,
  query: null,
  count: null,
  country_code: null,
  language_code: null,
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


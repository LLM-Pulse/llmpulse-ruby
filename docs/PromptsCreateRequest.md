# LLMPulse::PromptsCreateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **prompts** | **Array&lt;String&gt;** | Prompt texts (max 100). Each can be up to 2,000 bytes of UTF-8 text (about 2,000 characters in English, fewer with accented letters or non-Latin scripts). A new prompt over that returns ERR_INVALID_PARAM with error.meta.reason prompt_too_long and creates none of the batch; a text the project already tracks still comes back as exists. |  |
| **country_code** | **String** |  |  |
| **language_code** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptsCreateRequest.new(
  project_id: null,
  prompts: null,
  country_code: null,
  language_code: null
)
```


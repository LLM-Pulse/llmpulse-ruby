# LLMPulse::PromptsImportRequestRowsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompt** | **String** |  |  |
| **country_code** | **String** | ISO 3166-1 alpha-2 code or country name (default the project country) | [optional] |
| **language_code** | **String** | ISO language code or language name (default the project language) | [optional] |
| **tags** | **Array&lt;String&gt;** | Tag names for this prompt, created when missing | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptsImportRequestRowsInner.new(
  prompt: null,
  country_code: null,
  language_code: null,
  tags: null
)
```


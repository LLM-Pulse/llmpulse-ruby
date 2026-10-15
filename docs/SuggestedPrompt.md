# LLMPulse::SuggestedPrompt

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **prompt** | **String** |  |  |
| **source** | **String** | The generator that wrote it: website, magic (keyword runs), topic, reddit, paa, reputational, translate, gsc (Search Console) or catalog |  |
| **status** | **String** | pending, accepted or rejected |  |
| **country_code** | **String** |  |  |
| **language_code** | **String** |  |  |
| **prompt_id** | **Integer** | The prompt an accepted suggestion became |  |
| **accepted_at** | **Time** |  |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SuggestedPrompt.new(
  id: null,
  prompt: null,
  source: null,
  status: null,
  country_code: null,
  language_code: null,
  prompt_id: null,
  accepted_at: null,
  created_at: null
)
```


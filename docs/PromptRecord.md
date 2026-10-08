# LLMPulse::PromptRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **prompt_text** | **String** |  |  |
| **collection_id** | **Integer** | Primary tag, when the prompt has one |  |
| **collection_ids** | **Array&lt;Integer&gt;** | Every tag the prompt belongs to |  |
| **tags** | [**Array&lt;TagRef&gt;**](TagRef.md) |  |  |
| **country_code** | **String** |  |  |
| **language_code** | **String** |  |  |
| **prompt_type** | **String** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified |  |
| **brand_kind** | **String** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified |  |
| **last_executed_at** | **Time** | Null until the prompt has run |  |
| **app_url** | **String** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptRecord.new(
  id: null,
  prompt_text: null,
  collection_id: null,
  collection_ids: null,
  tags: null,
  country_code: null,
  language_code: null,
  prompt_type: null,
  brand_kind: null,
  last_executed_at: null,
  app_url: null
)
```


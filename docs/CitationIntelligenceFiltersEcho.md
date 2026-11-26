# LLMPulse::CitationIntelligenceFiltersEcho

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **model** | **String** |  | [optional] |
| **collection_id** | **String** | The collection_id parameter as sent (one id or a comma-separated list) | [optional] |
| **collection_ids** | **Array&lt;Integer&gt;** |  | [optional] |
| **domains** | **Array&lt;String&gt;** | Lowercased domains | [optional] |
| **prompt** | **Integer** | The prompt id filter | [optional] |
| **brand_kind** | **String** |  | [optional] |
| **country_code** | **String** |  | [optional] |
| **language_code** | **String** |  | [optional] |
| **from** | **String** | As given | [optional] |
| **to** | **String** | As given | [optional] |
| **key** | **String** | The group key, as matched | [optional] |
| **query** | **String** |  | [optional] |
| **source_type** | **String** |  | [optional] |
| **sentiment** | **String** |  | [optional] |
| **content_gap** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationIntelligenceFiltersEcho.new(
  model: null,
  collection_id: null,
  collection_ids: null,
  domains: null,
  prompt: null,
  brand_kind: null,
  country_code: null,
  language_code: null,
  from: null,
  to: null,
  key: null,
  query: null,
  source_type: null,
  sentiment: null,
  content_gap: null
)
```


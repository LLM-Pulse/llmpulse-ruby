# LLMPulse::CitationPageDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **url_sha256** | **String** |  |  |
| **normalized_url** | **String** |  |  |
| **page_cache** | [**CitationPageCache**](CitationPageCache.md) |  |  |
| **page_mentions** | [**CitationPageMentions**](CitationPageMentions.md) |  |  |
| **content** | [**CitationPageDetailsContent**](CitationPageDetailsContent.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationPageDetails.new(
  url_sha256: null,
  normalized_url: null,
  page_cache: null,
  page_mentions: null,
  content: null
)
```


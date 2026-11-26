# LLMPulse::CitationPageMentions

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **brand_mentioned** | **Boolean** |  |  |
| **competitor_mentioned** | **Boolean** |  |  |
| **brand_position** | **Integer** | Rank of the brand&#39;s first mention on the page; null when it has none |  |
| **content_gap_status** | **String** | missing_page_cache, content_unavailable, mentions_not_processed, mentioned, gap (a competitor but not the brand) or not_mentioned |  |
| **brands** | [**Array&lt;CitationPageMentionsBrandsInner&gt;**](CitationPageMentionsBrandsInner.md) | Each brand the page mentions once, in order of first mention |  |
| **mentions** | [**Array&lt;CitationPageMentionsMentionsInner&gt;**](CitationPageMentionsMentionsInner.md) | Every mention on the page with its snippet; not sent on GET /citation_intelligence/groups | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationPageMentions.new(
  brand_mentioned: null,
  competitor_mentioned: null,
  brand_position: null,
  content_gap_status: null,
  brands: null,
  mentions: null
)
```


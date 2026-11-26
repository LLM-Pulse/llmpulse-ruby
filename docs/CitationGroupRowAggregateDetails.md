# LLMPulse::CitationGroupRowAggregateDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **unique_urls_count** | **Integer** |  |  |
| **crawled_urls_count** | **Integer** | Pages with usable content |  |
| **brand_mentioned_urls_count** | **Integer** | Pages analyzed for the project that mention the brand; null when none is analyzed |  |
| **competitor_mentioned_urls_count** | **Integer** | Pages analyzed for the project that mention a competitor; null when none is analyzed |  |
| **last_crawled_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationGroupRowAggregateDetails.new(
  unique_urls_count: null,
  crawled_urls_count: null,
  brand_mentioned_urls_count: null,
  competitor_mentioned_urls_count: null,
  last_crawled_at: null
)
```


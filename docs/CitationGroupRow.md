# LLMPulse::CitationGroupRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **source_id** | **Integer** | The group&#39;s first citation |  |
| **view** | **String** | url, domain or host |  |
| **key** | **String** | The URL as cited, the domain or the host |  |
| **total_responses** | **Integer** | Answers citing it |  |
| **total_citations** | **Integer** |  |  |
| **citation_rate** | **Float** | total_responses as a percentage (0-100) of citation_rate_denominator |  |
| **citation_rate_denominator** | **Integer** | Answers matching the filters |  |
| **avg_citation_position** | **Float** | Null when no visible citation has a rank |  |
| **first_seen_at** | **Time** |  |  |
| **last_seen_at** | **Time** |  |  |
| **models** | **Hash&lt;String, Integer&gt;** | Answers citing it per AI model, keyed by model |  |
| **url** | **String** | url view only. The URL as cited | [optional] |
| **url_sha256** | **String** | url view only. Key of the cited page, shared by the URL&#39;s variants | [optional] |
| **normalized_url** | **String** | url view only | [optional] |
| **page_cache** | [**CitationPageCache**](CitationPageCache.md) |  | [optional] |
| **page_mentions** | [**CitationPageMentions**](CitationPageMentions.md) |  | [optional] |
| **domain** | **String** | domain view only | [optional] |
| **host** | **String** | host view only | [optional] |
| **aggregate_details** | [**CitationGroupRowAggregateDetails**](CitationGroupRowAggregateDetails.md) |  | [optional] |
| **citation_series** | [**CitationSeries**](CitationSeries.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationGroupRow.new(
  source_id: null,
  view: null,
  key: null,
  total_responses: null,
  total_citations: null,
  citation_rate: null,
  citation_rate_denominator: null,
  avg_citation_position: null,
  first_seen_at: null,
  last_seen_at: null,
  models: null,
  url: null,
  url_sha256: null,
  normalized_url: null,
  page_cache: null,
  page_mentions: null,
  domain: null,
  host: null,
  aggregate_details: null,
  citation_series: null
)
```


# LLMPulse::CitedUrlDetailsResponseStats

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_responses** | **Integer** | Answers citing the URL under the filters |  |
| **total_citations** | **Integer** |  |  |
| **citation_rate** | **Float** | total_responses as a percentage (0-100) of citation_rate_denominator |  |
| **citation_rate_denominator** | **Integer** | Answers matching the filters |  |
| **avg_citation_position** | **Float** | Null when no visible citation has a rank |  |
| **first_seen_at** | **Time** | Null when no citation matches the filters |  |
| **last_seen_at** | **Time** | Null when no citation matches the filters |  |
| **distinct_urls** | **Integer** | Spellings of the URL cited (tracking parameters, a trailing slash) |  |
| **source_types** | [**CitedUrlDetailsResponseStatsSourceTypes**](CitedUrlDetailsResponseStatsSourceTypes.md) |  |  |
| **models** | **Hash&lt;String, Integer&gt;** | Answers citing the URL per AI model, keyed by model |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitedUrlDetailsResponseStats.new(
  total_responses: null,
  total_citations: null,
  citation_rate: null,
  citation_rate_denominator: null,
  avg_citation_position: null,
  first_seen_at: null,
  last_seen_at: null,
  distinct_urls: null,
  source_types: null,
  models: null
)
```


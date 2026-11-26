# LLMPulse::CitedUrlDetailsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **url_sha256** | **String** |  |  |
| **url** | **String** | The URL as first cited |  |
| **normalized_url** | **String** |  |  |
| **domain** | **String** |  |  |
| **host** | **String** |  |  |
| **stats** | [**CitedUrlDetailsResponseStats**](CitedUrlDetailsResponseStats.md) |  |  |
| **urls** | **Array&lt;String&gt;** | Up to 20 spellings of the URL as cited, alphabetically |  |
| **page_details** | [**CitationPageDetails**](CitationPageDetails.md) |  |  |
| **citation_series** | [**CitationSeries**](CitationSeries.md) |  | [optional] |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitedUrlDetailsResponse.new(
  project_id: null,
  url_sha256: null,
  url: null,
  normalized_url: null,
  domain: null,
  host: null,
  stats: null,
  urls: null,
  page_details: null,
  citation_series: null,
  request_id: null
)
```


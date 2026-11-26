# LLMPulse::CitedUrlContentResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **url_sha256** | **String** |  |  |
| **url** | **String** | The URL as first cited |  |
| **normalized_url** | **String** |  |  |
| **domain** | **String** |  |  |
| **host** | **String** |  |  |
| **page_details** | [**CitationPageDetails**](CitationPageDetails.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitedUrlContentResponse.new(
  project_id: null,
  url_sha256: null,
  url: null,
  normalized_url: null,
  domain: null,
  host: null,
  page_details: null,
  request_id: null
)
```


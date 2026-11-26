# LLMPulse::CitedUrlOccurrencesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **url_sha256** | **String** |  |  |
| **data** | [**Array&lt;CitedUrlOccurrencesResponseAllOfData&gt;**](CitedUrlOccurrencesResponseAllOfData.md) | One row per citation of the URL, latest answer first |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitedUrlOccurrencesResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  url_sha256: null,
  data: null
)
```


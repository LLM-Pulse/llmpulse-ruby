# LLMPulse::UrlListDetailResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **url_list** | [**UrlList**](UrlList.md) |  |  |
| **filters** | [**UrlListFilters**](UrlListFilters.md) |  |  |
| **summary** | [**UrlListSummary**](UrlListSummary.md) |  |  |
| **status_counts** | [**UrlListStatusCounts**](UrlListStatusCounts.md) |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** |  |  |
| **entries** | [**Array&lt;UrlListEntry&gt;**](UrlListEntry.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UrlListDetailResponse.new(
  project_id: null,
  url_list: null,
  filters: null,
  summary: null,
  status_counts: null,
  page: null,
  per_page: null,
  total: null,
  entries: null,
  request_id: null
)
```


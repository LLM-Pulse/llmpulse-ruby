# LLMPulse::CmsContentListResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **site** | [**CmsSite**](CmsSite.md) |  | [optional] |
| **type** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **total_pages** | **Integer** |  | [optional] |
| **data** | [**Array&lt;CmsContentSummary&gt;**](CmsContentSummary.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CmsContentListResponse.new(
  project_id: null,
  site: null,
  type: null,
  status: null,
  page: null,
  per_page: null,
  total: null,
  total_pages: null,
  data: null,
  request_id: null
)
```


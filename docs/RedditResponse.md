# LLMPulse::RedditResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **page** | **Integer** |  |  |
| **per_page** | **Integer** |  |  |
| **total** | **Integer** | Rows matching the filters across every page |  |
| **request_id** | **String** |  |  |
| **view** | **String** | subreddits, authors, threads or breakdowns |  |
| **from** | **Time** | Start of the window, 30 days back by default |  |
| **to** | **Time** |  |  |
| **citations** | **Integer** | Reddit citations after the filters (view&#x3D;breakdowns) | [optional] |
| **data** | [**Array&lt;RedditRow&gt;**](RedditRow.md) |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::RedditResponse.new(
  project_id: null,
  page: null,
  per_page: null,
  total: null,
  request_id: null,
  view: null,
  from: null,
  to: null,
  citations: null,
  data: null
)
```


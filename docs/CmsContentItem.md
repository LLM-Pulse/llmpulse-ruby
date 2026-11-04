# LLMPulse::CmsContentItem

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | WordPress post or page id | [optional] |
| **type** | **String** |  | [optional] |
| **status** | **String** | WordPress status (publish, future, draft, pending or private) | [optional] |
| **slug** | **String** |  | [optional] |
| **title** | **String** | Plain-text title as the site renders it | [optional] |
| **url** | **String** | The public link on the connected site; null when the site names a link on another host | [optional] |
| **modified_at** | **Time** |  | [optional] |
| **excerpt** | **String** | Plain-text excerpt, up to 2,000 characters | [optional] |
| **content_html** | **String** | Sanitized HTML (headings, paragraphs, lists, tables, quotes, code, links with href only), up to 200,000 characters | [optional] |
| **content_truncated** | **Boolean** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CmsContentItem.new(
  id: null,
  type: null,
  status: null,
  slug: null,
  title: null,
  url: null,
  modified_at: null,
  excerpt: null,
  content_html: null,
  content_truncated: null
)
```


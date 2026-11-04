# LLMPulse::CmsContentSummary

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

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CmsContentSummary.new(
  id: null,
  type: null,
  status: null,
  slug: null,
  title: null,
  url: null,
  modified_at: null
)
```


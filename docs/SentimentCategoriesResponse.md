# LLMPulse::SentimentCategoriesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **sentiments** | [**Array&lt;SentimentCategory&gt;**](SentimentCategory.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SentimentCategoriesResponse.new(
  project_id: null,
  sentiments: null,
  request_id: null
)
```


# LLMPulse::RedditAuthorBrand

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **is_brand** | **Boolean** | True for your own brand |  |
| **id** | **Integer** | The competitor&#39;s id; null for your own brand |  |
| **name** | **String** |  |  |
| **count** | **Integer** | The author&#39;s cited posts whose content names the brand |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::RedditAuthorBrand.new(
  is_brand: null,
  id: null,
  name: null,
  count: null
)
```


# LLMPulse::OwnedMediaCitedItem

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **kind** | **String** | post covers posts and videos, profile covers profiles and channels | [optional] |
| **title** | **String** |  | [optional] |
| **subtitle** | **String** |  | [optional] |
| **url** | **String** |  | [optional] |
| **image_url** | **String** |  | [optional] |
| **yours** | **Boolean** |  | [optional] |
| **date** | **Time** | Publication date of a post or video | [optional] |
| **stats** | [**OwnedMediaCitedItemStats**](OwnedMediaCitedItemStats.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaCitedItem.new(
  kind: null,
  title: null,
  subtitle: null,
  url: null,
  image_url: null,
  yours: null,
  date: null,
  stats: null
)
```


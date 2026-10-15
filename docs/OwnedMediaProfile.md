# LLMPulse::OwnedMediaProfile

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **url** | **String** |  | [optional] |
| **handle** | **String** | The handle, page id, store app id, subreddit or username | [optional] |
| **kind** | **String** |  | [optional] |
| **main** | **Boolean** | True for the main profile of its platform (or store), false for an extra one | [optional] |
| **store** | **String** | google_play or app_store for an app; null elsewhere | [optional] |
| **name** | **String** |  | [optional] |
| **avatar_url** | **String** |  | [optional] |
| **scrape_status** | **String** | State of the profile scrape that reads its name and avatar: pending, running, ready, failed or skipped; null when none has started or the platform has none | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaProfile.new(
  url: null,
  handle: null,
  kind: null,
  main: null,
  store: null,
  name: null,
  avatar_url: null,
  scrape_status: null
)
```


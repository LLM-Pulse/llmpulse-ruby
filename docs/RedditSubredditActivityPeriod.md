# LLMPulse::RedditSubredditActivityPeriod

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Date** | Start date of the actual reporting period |  |
| **subreddit** | **String** | Subreddit name, or null for the Others aggregate |  |
| **is_others** | **Boolean** |  |  |
| **citations** | **Integer** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::RedditSubredditActivityPeriod.new(
  date: null,
  subreddit: null,
  is_others: null,
  citations: null
)
```


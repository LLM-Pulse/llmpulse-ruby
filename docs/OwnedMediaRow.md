# LLMPulse::OwnedMediaRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Date** | The start date of the actual reporting period (view&#x3D;activity) | [optional] |
| **entity_id** | **String** | Platform entity identifier (view&#x3D;activity) | [optional] |
| **entity_name** | **String** | Current entity name when known (view&#x3D;activity) | [optional] |
| **entity_url** | **String** | Current profile, channel or app listing URL when known (view&#x3D;activity) | [optional] |
| **store** | **String** | Store selected for provider&#x3D;mobile_apps (view&#x3D;activity) | [optional] |
| **competitor_id** | **Integer** | Competitor identifier when the activity row represents a competitor app | [optional] |
| **title** | **String** |  | [optional] |
| **url** | **String** |  | [optional] |
| **channel_name** | **String** |  | [optional] |
| **channel_handle** | **String** | The video&#39;s channel handle, without the @ | [optional] |
| **channel_url** | **String** |  | [optional] |
| **video_id** | **String** |  | [optional] |
| **key** | **String** | The channel key (handle:..., channel:... or name:...), accepted as profile by /dimensions/owned_media/citing_prompts | [optional] |
| **name** | **String** |  | [optional] |
| **handle** | **String** |  | [optional] |
| **caption** | **String** |  | [optional] |
| **owner_handle** | **String** |  | [optional] |
| **thumbnail_url** | **String** | The post or video image. Our cached copy where one exists, so the link does not expire | [optional] |
| **avatar_url** | **String** | The profile or channel image. Our cached copy where one exists | [optional] |
| **content_type** | **String** | The post format on its platform: reel, post or tv on Instagram, post or pulse on LinkedIn, post elsewhere | [optional] |
| **citations** | **Integer** | Citations for the row; for view&#x3D;activity, the count in this reporting period | [optional] |
| **unique_videos** | **Integer** |  | [optional] |
| **unique_posts** | **Integer** |  | [optional] |
| **followers** | **Integer** |  | [optional] |
| **likes** | **Integer** |  | [optional] |
| **comments** | **Integer** |  | [optional] |
| **views** | **Object** | View count as the platform reports it, a number or a numeric string, or null when unknown | [optional] |
| **published_at** | **String** | Publication date as the platform reports it | [optional] |
| **posted_at** | **String** | Publication date as the platform reports it (ISO 8601, or Unix seconds on TikTok) | [optional] |
| **avg_position** | **Float** | Average position of the citation in the answers (1 &#x3D; first); null when unknown | [optional] |
| **yours** | **Boolean** |  | [optional] |
| **citation_date** | **Time** |  | [optional] |
| **position** | **Integer** |  | [optional] |
| **model** | **String** |  | [optional] |
| **domain** | **String** | The app&#39;s store listing URL (provider&#x3D;mobile_apps) | [optional] |
| **total_responses** | **Integer** |  | [optional] |
| **rank** | **Integer** |  | [optional] |
| **global_rank** | **Integer** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaRow.new(
  date: null,
  entity_id: null,
  entity_name: null,
  entity_url: null,
  store: null,
  competitor_id: null,
  title: null,
  url: null,
  channel_name: null,
  channel_handle: null,
  channel_url: null,
  video_id: null,
  key: null,
  name: null,
  handle: null,
  caption: null,
  owner_handle: null,
  thumbnail_url: null,
  avatar_url: null,
  content_type: null,
  citations: null,
  unique_videos: null,
  unique_posts: null,
  followers: null,
  likes: null,
  comments: null,
  views: null,
  published_at: null,
  posted_at: null,
  avg_position: null,
  yours: null,
  citation_date: null,
  position: null,
  model: null,
  domain: null,
  total_responses: null,
  rank: null,
  global_rank: null
)
```


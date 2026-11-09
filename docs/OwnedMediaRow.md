# LLMPulse::OwnedMediaRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Date** | The start date of the actual reporting period (view&#x3D;activity) | [optional] |
| **entity_id** | **String** | Platform entity identifier (view&#x3D;activity) | [optional] |
| **entity_name** | **String** | Current entity name when known (view&#x3D;activity) | [optional] |
| **entity_url** | **String** | Current profile, channel or app listing URL when known (view&#x3D;activity) | [optional] |
| **store** | **String** | Store selected for provider&#x3D;mobile_apps (view&#x3D;activity) | [optional] |
| **competitor_id** | **Integer** | Competitor identifier when the row represents a competitor&#39;s app or Trustpilot profile | [optional] |
| **id** | **Integer** | The review&#39;s identifier (provider&#x3D;trustpilot, view&#x3D;reviews) | [optional] |
| **brand** | **String** | The brand or competitor whose Trustpilot profile carries the review (provider&#x3D;trustpilot, view&#x3D;reviews) | [optional] |
| **rating** | **Float** | Trustpilot rating out of 5: the profile&#39;s at its last monthly read (views profiles and brands) or the review&#39;s stars (view&#x3D;reviews) | [optional] |
| **rating_change** | **Float** | Change of the profile&#39;s rating since the previous monthly read (provider&#x3D;trustpilot, view&#x3D;brands); null before a second read | [optional] |
| **reviews_count** | **Integer** | The profile&#39;s review count on Trustpilot at its last monthly read (provider&#x3D;trustpilot) | [optional] |
| **status** | **String** | Whether the brand&#39;s Trustpilot profile has been read (found), Trustpilot has no business for its domain (not_found), or it has not been read yet (pending) (provider&#x3D;trustpilot, view&#x3D;brands) | [optional] |
| **text** | **String** | The review text (provider&#x3D;trustpilot, view&#x3D;reviews) | [optional] |
| **author** | **String** | The reviewer&#39;s display name (provider&#x3D;trustpilot, view&#x3D;reviews) | [optional] |
| **replied** | **Boolean** | Whether the business replied to the review (provider&#x3D;trustpilot, view&#x3D;reviews) | [optional] |
| **title** | **String** |  | [optional] |
| **url** | **String** |  | [optional] |
| **channel_name** | **String** |  | [optional] |
| **channel_handle** | **String** | The video&#39;s channel handle, without the @ | [optional] |
| **channel_url** | **String** |  | [optional] |
| **video_id** | **String** |  | [optional] |
| **key** | **String** | The channel key (handle:..., channel:... or name:...), accepted as profile by /dimensions/owned_media/citing_prompts; on provider&#x3D;trustpilot, the business domain the profile is filed under, null for a brand without a domain | [optional] |
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
| **domain** | **String** | The app&#39;s store listing URL (provider&#x3D;mobile_apps), or the brand&#39;s domain (provider&#x3D;trustpilot, view&#x3D;brands) | [optional] |
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
  id: null,
  brand: null,
  rating: null,
  rating_change: null,
  reviews_count: null,
  status: null,
  text: null,
  author: null,
  replied: null,
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


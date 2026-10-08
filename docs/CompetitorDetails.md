# LLMPulse::CompetitorDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **project_id** | **Integer** |  | [optional] |
| **brand_name** | **String** |  | [optional] |
| **domain** | **String** |  | [optional] |
| **matching_names** | **Array&lt;String&gt;** |  | [optional] |
| **google_play_id** | **String** |  | [optional] |
| **app_store_id** | **String** |  | [optional] |
| **citation_match_mode** | [**CitationMatchMode**](CitationMatchMode.md) |  | [optional] |
| **citation_match_path** | **String** | Set only when citation_match_mode is path_prefix | [optional] |
| **google_play_name** | **String** | English app name on Google Play, when the competitor has an Android app | [optional] |
| **app_store_name** | **String** | English app name on the App Store, when the competitor has an iOS app | [optional] |
| **google_play_icon_url** | **String** |  | [optional] |
| **app_store_icon_url** | **String** |  | [optional] |
| **color** | **String** |  | [optional] |
| **processing** | **Boolean** | True while the competitor&#39;s historical mentions are being recalculated | [optional] |
| **created_at** | **Time** |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CompetitorDetails.new(
  id: null,
  project_id: null,
  brand_name: null,
  domain: null,
  matching_names: null,
  google_play_id: null,
  app_store_id: null,
  citation_match_mode: null,
  citation_match_path: null,
  google_play_name: null,
  app_store_name: null,
  google_play_icon_url: null,
  app_store_icon_url: null,
  color: null,
  processing: null,
  created_at: null,
  request_id: null
)
```


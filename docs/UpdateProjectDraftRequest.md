# LLMPulse::UpdateProjectDraftRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **step** | **String** |  |  |
| **name** | **String** |  | [optional] |
| **brand_name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **industry** | **Array&lt;String&gt;** |  | [optional] |
| **matching_names** | **Array&lt;String&gt;** |  | [optional] |
| **external_identifier** | **String** |  | [optional] |
| **prompts** | **Array&lt;String&gt;** |  | [optional] |
| **competitors** | **Array&lt;Object&gt;** |  | [optional] |
| **youtube_channel_url** | **String** |  | [optional] |
| **instagram_profile_url** | **String** |  | [optional] |
| **facebook_page_url** | **String** |  | [optional] |
| **tiktok_profile_url** | **String** |  | [optional] |
| **app_store_url** | **String** |  | [optional] |
| **google_play_url** | **String** |  | [optional] |
| **suggest** | **Boolean** |  | [optional][default to true] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UpdateProjectDraftRequest.new(
  step: null,
  name: null,
  brand_name: null,
  description: null,
  industry: null,
  matching_names: null,
  external_identifier: null,
  prompts: null,
  competitors: null,
  youtube_channel_url: null,
  instagram_profile_url: null,
  facebook_page_url: null,
  tiktok_profile_url: null,
  app_store_url: null,
  google_play_url: null,
  suggest: null
)
```


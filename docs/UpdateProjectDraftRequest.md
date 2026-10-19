# LLMPulse::UpdateProjectDraftRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **step** | **String** |  |  |
| **name** | **String** |  | [optional] |
| **brand_name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **industry** | **Array&lt;String&gt;** |  | [optional] |
| **matching_names** | **Array&lt;String&gt;** | Brand-name variants used to detect mentions (details step). At most 50 names of up to 100 characters each; the step stores the list as sent, and finalize refuses a longer list or name with ERR_INVALID_PARAM (422) | [optional] |
| **external_identifier** | **String** |  | [optional] |
| **prompts** | **Array&lt;String&gt;** |  | [optional] |
| **competitors** | **Array&lt;Object&gt;** | Competitors step: objects {domain, brand_name, matching_names}, capped by plan. Each competitor&#39;s matching_names takes at most 50 names of up to 100 characters, checked at finalize like POST /projects | [optional] |
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


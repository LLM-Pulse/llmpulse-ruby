# LLMPulse::UpdateOwnedMediaProfilesRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **youtube_channel_url** | **String** | The main YouTube channel URL (@handle, /channel/UC..., /c/... or /user/...). An empty string or null clears it | [optional] |
| **app_store_url** | **String** | The App Store app URL, with its id number. An empty string or null clears it | [optional] |
| **google_play_url** | **String** | The Google Play app URL, or its package name (com.acme.app). An empty string or null clears it | [optional] |
| **instagram_profile_url** | **String** | The main Instagram profile URL. An empty string or null clears it | [optional] |
| **facebook_page_url** | **String** | The main Facebook Page URL. An empty string or null clears it | [optional] |
| **tiktok_profile_url** | **String** | The main TikTok profile URL. An empty string or null clears it | [optional] |
| **linkedin_company_url** | **String** | The main LinkedIn page URL: a company (/company/...), school (/school/...) or showcase (/showcase/...) page. An empty string or null clears it | [optional] |
| **youtube_extra_profile_urls** | **Array&lt;String&gt;** | FULL replacement list of extra YouTube channel URLs (at most 10); [] clears it | [optional] |
| **mobile_apps_extra_profile_urls** | **Array&lt;String&gt;** | FULL replacement list of extra App Store or Google Play app URLs (at most 10); [] clears it | [optional] |
| **instagram_extra_profile_urls** | **Array&lt;String&gt;** | FULL replacement list of extra Instagram profile URLs (at most 10); [] clears it | [optional] |
| **facebook_extra_profile_urls** | **Array&lt;String&gt;** | FULL replacement list of extra Facebook Page URLs (at most 10); [] clears it | [optional] |
| **tiktok_extra_profile_urls** | **Array&lt;String&gt;** | FULL replacement list of extra TikTok profile URLs (at most 10); [] clears it | [optional] |
| **linkedin_extra_profile_urls** | **Array&lt;String&gt;** | FULL replacement list of extra LinkedIn company, school or showcase page URLs (at most 10); [] clears it | [optional] |
| **reddit_subreddits** | **Array&lt;String&gt;** | FULL replacement list (at most 10) of subreddit names the brand owns, without r/; [] clears it | [optional] |
| **reddit_usernames** | **Array&lt;String&gt;** | FULL replacement list (at most 25) of Reddit usernames the brand owns, without u/; [] clears it | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UpdateOwnedMediaProfilesRequest.new(
  youtube_channel_url: null,
  app_store_url: null,
  google_play_url: null,
  instagram_profile_url: null,
  facebook_page_url: null,
  tiktok_profile_url: null,
  linkedin_company_url: null,
  youtube_extra_profile_urls: null,
  mobile_apps_extra_profile_urls: null,
  instagram_extra_profile_urls: null,
  facebook_extra_profile_urls: null,
  tiktok_extra_profile_urls: null,
  linkedin_extra_profile_urls: null,
  reddit_subreddits: null,
  reddit_usernames: null
)
```


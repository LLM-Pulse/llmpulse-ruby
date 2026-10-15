# LLMPulse::OwnedMediaProfilesUpdateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **platforms** | [**Array&lt;OwnedMediaPlatformProfiles&gt;**](OwnedMediaPlatformProfiles.md) |  | [optional] |
| **settings** | [**OwnedMediaProfileSettings**](OwnedMediaProfileSettings.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |
| **updated_fields** | **Array&lt;String&gt;** | The fields this request set | [optional] |
| **profile_scrapes_queued** | **Array&lt;String&gt;** | Platforms whose new profile is being scraped in the background for its name and avatar | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaProfilesUpdateResponse.new(
  project_id: null,
  platforms: null,
  settings: null,
  request_id: null,
  updated_fields: null,
  profile_scrapes_queued: null
)
```


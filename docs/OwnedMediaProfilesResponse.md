# LLMPulse::OwnedMediaProfilesResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **platforms** | [**Array&lt;OwnedMediaPlatformProfiles&gt;**](OwnedMediaPlatformProfiles.md) |  | [optional] |
| **settings** | [**OwnedMediaProfileSettings**](OwnedMediaProfileSettings.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaProfilesResponse.new(
  project_id: null,
  platforms: null,
  settings: null,
  request_id: null
)
```


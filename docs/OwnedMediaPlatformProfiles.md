# LLMPulse::OwnedMediaPlatformProfiles

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **platform** | **String** |  | [optional] |
| **connected** | **Boolean** |  | [optional] |
| **max_extra_profiles** | **Integer** | How many extra profiles the platform accepts; null where it takes none | [optional] |
| **profiles** | [**Array&lt;OwnedMediaProfile&gt;**](OwnedMediaProfile.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaPlatformProfiles.new(
  platform: null,
  connected: null,
  max_extra_profiles: null,
  profiles: null
)
```


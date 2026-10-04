# LLMPulse::AiOrdersUpdateResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **platform** | **String** |  |  |
| **stored** | **Integer** | Rows stored, one per day and AI assistant |  |
| **ignored** | **Integer** | Entries whose referrer is not an AI assistant |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiOrdersUpdateResponse.new(
  project_id: null,
  platform: null,
  stored: null,
  ignored: null,
  request_id: null
)
```


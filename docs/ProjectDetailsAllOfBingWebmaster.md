# LLMPulse::ProjectDetailsAllOfBingWebmaster

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **site** | **String** | The connected site (e.g. https://example.com/), null when not connected | [optional] |
| **last_synced_at** | **Time** | When that site last synced, null before its first sync | [optional] |
| **connect_url** | **String** | The in-app page where the site is connected or reconnected (Preferences &gt; Project Settings &gt; Connections) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetailsAllOfBingWebmaster.new(
  status: null,
  site: null,
  last_synced_at: null,
  connect_url: null
)
```


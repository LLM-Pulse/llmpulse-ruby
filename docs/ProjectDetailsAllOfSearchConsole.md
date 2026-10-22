# LLMPulse::ProjectDetailsAllOfSearchConsole

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **property** | **String** | The connected property (e.g. sc-domain:example.com), null when not connected | [optional] |
| **connect_url** | **String** | The in-app page where the property is connected or reconnected (Preferences &gt; Project Settings &gt; Data Connections) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetailsAllOfSearchConsole.new(
  status: null,
  property: null,
  connect_url: null
)
```


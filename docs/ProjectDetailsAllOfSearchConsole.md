# LLMPulse::ProjectDetailsAllOfSearchConsole

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **property** | **String** | The primary property (e.g. sc-domain:example.com), null when not connected | [optional] |
| **connect_url** | **String** | The in-app page where the property is connected or reconnected (Preferences &gt; Project Settings &gt; Data Connections) | [optional] |
| **properties_count** | **Integer** | Connected properties Google still accepts (reconnect_required ones excluded); GET /search_console/properties lists every property with its status | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetailsAllOfSearchConsole.new(
  status: null,
  property: null,
  connect_url: null,
  properties_count: null
)
```


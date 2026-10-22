# LLMPulse::ProjectDetailsAllOfAgentTraffic

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **status** | **String** |  | [optional] |
| **provider** | **String** | The connected source (e.g. cloudflare_graphql, bunny_cdn, s3 or the log drain&#39;s provider), null without a live source | [optional] |
| **connect_url** | **String** | The in-app Agent Analytics page, where a source is connected or reconnected | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetailsAllOfAgentTraffic.new(
  status: null,
  provider: null,
  connect_url: null
)
```


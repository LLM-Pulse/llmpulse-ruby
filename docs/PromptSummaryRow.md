# LLMPulse::PromptSummaryRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prompt_id** | **Integer** |  | [optional] |
| **prompt_text** | **String** |  | [optional] |
| **model** | **String** | Only present when breakdown&#x3D;model | [optional] |
| **responses** | **Integer** |  | [optional] |
| **mentions** | **Integer** |  | [optional] |
| **citations** | **Integer** |  | [optional] |
| **visibility** | **Float** |  | [optional] |
| **mention_rate** | **Float** |  | [optional] |
| **citation_rate** | **Float** |  | [optional] |
| **avg_mention_position** | **Float** |  | [optional] |
| **avg_position** | **Float** |  | [optional] |
| **app_url** | **String** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptSummaryRow.new(
  prompt_id: null,
  prompt_text: null,
  model: null,
  responses: null,
  mentions: null,
  citations: null,
  visibility: null,
  mention_rate: null,
  citation_rate: null,
  avg_mention_position: null,
  avg_position: null,
  app_url: null
)
```


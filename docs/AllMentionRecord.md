# LLMPulse::AllMentionRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | The mention&#39;s id, unique within its actor_type |  |
| **actor_type** | **String** | project (your brand) or competitor |  |
| **competitor_id** | **Integer** | Competitor rows only | [optional] |
| **name** | **String** | The project&#39;s brand name (its name when no brand name is set), or the competitor&#39;s brand name |  |
| **domain** | **String** | The competitor&#39;s bare domain (competitor rows only) | [optional] |
| **prompt_id** | **Integer** |  |  |
| **prompt_execution_id** | **Integer** |  |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AllMentionRecord.new(
  id: null,
  actor_type: null,
  competitor_id: null,
  name: null,
  domain: null,
  prompt_id: null,
  prompt_execution_id: null,
  created_at: null
)
```


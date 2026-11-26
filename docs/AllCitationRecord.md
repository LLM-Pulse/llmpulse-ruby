# LLMPulse::AllCitationRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | The citation&#39;s id, unique within its actor_type |  |
| **actor_type** | **String** | project (your brand) or competitor |  |
| **competitor_id** | **Integer** | Competitor rows only | [optional] |
| **name** | **String** | The project&#39;s brand name (its name when no brand name is set), or the competitor&#39;s brand name |  |
| **domain** | **String** | On project rows the host of the cited URL without www. (null when it has no parsable host); on competitor rows the competitor&#39;s bare domain |  |
| **prompt_id** | **Integer** |  |  |
| **prompt_execution_id** | **Integer** |  |  |
| **url** | **String** | Normalized cited URL (tracking parameters and fragment removed) |  |
| **position** | **Integer** | Rank of the citation in the answer; 0 for a background source reference with no visible rank |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AllCitationRecord.new(
  id: null,
  actor_type: null,
  competitor_id: null,
  name: null,
  domain: null,
  prompt_id: null,
  prompt_execution_id: null,
  url: null,
  position: null,
  created_at: null
)
```


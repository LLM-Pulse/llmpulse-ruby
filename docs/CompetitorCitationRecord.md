# LLMPulse::CompetitorCitationRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **competitor_id** | **Integer** |  |  |
| **name** | **String** | The competitor&#39;s brand name |  |
| **domain** | **String** | The competitor&#39;s bare domain |  |
| **prompt_execution_id** | **Integer** |  |  |
| **url** | **String** | Normalized cited URL (tracking parameters and fragment removed) |  |
| **position** | **Integer** | Rank of the citation in the answer; 0 for a background source reference with no visible rank |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CompetitorCitationRecord.new(
  id: null,
  competitor_id: null,
  name: null,
  domain: null,
  prompt_execution_id: null,
  url: null,
  position: null,
  created_at: null
)
```


# LLMPulse::CitationRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **name** | **String** | The project&#39;s brand name (its name when no brand name is set) |  |
| **domain** | **String** | Host of the cited URL without www.; null when the URL has no parsable host |  |
| **prompt_id** | **Integer** |  |  |
| **prompt_execution_id** | **Integer** |  |  |
| **url** | **String** | Normalized cited URL (tracking parameters and fragment removed) |  |
| **position** | **Integer** | Rank of the citation in the answer; 0 for a background source reference with no visible rank |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationRecord.new(
  id: null,
  name: null,
  domain: null,
  prompt_id: null,
  prompt_execution_id: null,
  url: null,
  position: null,
  created_at: null
)
```


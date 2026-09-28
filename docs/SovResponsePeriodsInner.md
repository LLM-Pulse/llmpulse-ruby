# LLMPulse::SovResponsePeriodsInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **Date** |  | [optional] |
| **mentions** | **Integer** |  | [optional] |
| **partial** | **Boolean** |  | [optional] |
| **confidence** | **String** | How far the shares of this period can be trusted, from its mentions: none (0), low (under 30), medium (under 100) or high (100 or more). | [optional] |
| **margin_of_error** | **Float** | Worst-case 95% margin of a share in percentage points, 98 / sqrt(mentions); mentions within one answer are not independent, so the real margin is at least this wide. null with no mentions. | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SovResponsePeriodsInner.new(
  date: null,
  mentions: null,
  partial: null,
  confidence: low,
  margin_of_error: 21.9
)
```


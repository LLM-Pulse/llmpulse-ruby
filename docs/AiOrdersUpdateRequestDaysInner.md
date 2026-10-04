# LLMPulse::AiOrdersUpdateRequestDaysInner

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **day** | **Date** | Must fall inside from..to |  |
| **referrer** | **String** | Raw referring host or utm_source of the order&#39;s first visit, e.g. chatgpt.com. Entries that are not an AI assistant are ignored |  |
| **orders** | **Integer** |  |  |
| **revenue** | **String** | Non-negative decimal amount in currency, e.g. 120.50. A JSON number is accepted too |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::AiOrdersUpdateRequestDaysInner.new(
  day: null,
  referrer: null,
  orders: null,
  revenue: null
)
```


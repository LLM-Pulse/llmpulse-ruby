# LLMPulse::ShoppingTotals

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **products** | **Integer** |  |  |
| **your_products** | **Integer** |  |  |
| **merchants** | **Integer** |  |  |
| **avg_price** | **Float** | Average price in avg_price_currency |  |
| **avg_price_currency** | **String** | The currency most prices use |  |
| **avg_rating** | **Float** |  |  |
| **executions_with_shopping** | **Integer** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ShoppingTotals.new(
  products: null,
  your_products: null,
  merchants: null,
  avg_price: null,
  avg_price_currency: null,
  avg_rating: null,
  executions_with_shopping: null
)
```


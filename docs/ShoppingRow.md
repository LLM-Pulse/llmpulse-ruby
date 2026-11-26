# LLMPulse::ShoppingRow

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **product_key** | **String** | Stable grouping key of the product: its external id, else title: and the lowercased title (view&#x3D;products) | [optional] |
| **title** | **String** |  | [optional] |
| **domain** | **String** |  | [optional] |
| **url** | **String** |  | [optional] |
| **merchants** | **String** | The merchants the product card names (view&#x3D;products) | [optional] |
| **merchant** | **String** | The merchant (view&#x3D;merchants) | [optional] |
| **products** | **Integer** | Distinct products the merchant sold (view&#x3D;merchants) | [optional] |
| **currency** | **String** | Currency code the prices are in; null when no price names one |  |
| **currency_count** | **Integer** | Currencies the product was priced in; above 1 the row reports its highest-priced listing (view&#x3D;products) | [optional] |
| **min_price** | **Float** |  |  |
| **max_price** | **Float** |  |  |
| **avg_price** | **Float** | Average price in currency (view&#x3D;merchants) | [optional] |
| **avg_rating** | **Float** |  |  |
| **rating_votes** | **Integer** | Most rating votes any listing of the product showed (view&#x3D;products) | [optional] |
| **appearances** | **Integer** |  |  |
| **is_client** | **Boolean** | Whether the product is identified as your brand&#39;s own (view&#x3D;products) | [optional] |
| **best_rank** | **Integer** | Best rank the product got in a card list (view&#x3D;products) | [optional] |
| **models** | **Array&lt;String&gt;** | Models that showed the product (view&#x3D;products) | [optional] |
| **last_seen_at** | **Time** | The latest answer that showed the product (view&#x3D;products) | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ShoppingRow.new(
  product_key: null,
  title: null,
  domain: null,
  url: null,
  merchants: null,
  merchant: null,
  products: null,
  currency: null,
  currency_count: null,
  min_price: null,
  max_price: null,
  avg_price: null,
  avg_rating: null,
  rating_votes: null,
  appearances: null,
  is_client: null,
  best_rank: null,
  models: null,
  last_seen_at: null
)
```


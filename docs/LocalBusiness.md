# LLMPulse::LocalBusiness

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **business_key** | **String** | Stable grouping key: the lowercased name and address | [optional] |
| **title** | **String** |  | [optional] |
| **address** | **String** |  | [optional] |
| **domain** | **String** |  | [optional] |
| **url** | **String** |  | [optional] |
| **phone** | **String** |  | [optional] |
| **avg_rating** | **Float** |  | [optional] |
| **reviews** | **Integer** |  | [optional] |
| **avg_position** | **Float** | Average rank of the business in the answer&#39;s list (1 &#x3D; first) | [optional] |
| **prompts** | **Integer** |  | [optional] |
| **appearances** | **Integer** |  | [optional] |
| **is_client** | **Boolean** |  | [optional] |
| **competitor_id** | **Integer** |  | [optional] |
| **competitor_name** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::LocalBusiness.new(
  business_key: null,
  title: null,
  address: null,
  domain: null,
  url: null,
  phone: null,
  avg_rating: null,
  reviews: null,
  avg_position: null,
  prompts: null,
  appearances: null,
  is_client: null,
  competitor_id: null,
  competitor_name: null
)
```


# LLMPulse::CatalogProduct

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **external_id** | **String** | The store&#39;s product id, e.g. gid://shopify/Product/1 |  |
| **title** | **String** |  |  |
| **handle** | **String** |  | [optional] |
| **product_type** | **String** |  | [optional] |
| **vendor** | **String** |  | [optional] |
| **tags** | **Array&lt;String&gt;** |  | [optional] |
| **collections** | **Array&lt;String&gt;** |  | [optional] |
| **url** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CatalogProduct.new(
  external_id: null,
  title: null,
  handle: null,
  product_type: null,
  vendor: null,
  tags: null,
  collections: null,
  url: null
)
```


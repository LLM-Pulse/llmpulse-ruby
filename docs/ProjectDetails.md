# LLMPulse::ProjectDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **name** | **String** | Internal project label (sidebar, settings, admin) | [optional] |
| **brand_name** | **String** | LLM-facing brand label (used in prompts and customer-facing charts). Defaults to &#x60;name&#x60; when not set. | [optional] |
| **url** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **matching_names** | **Array&lt;String&gt;** |  | [optional] |
| **industry** | **String** |  | [optional] |
| **business_model** | **String** |  | [optional] |
| **business_model_other** | **String** | Set only when business_model is OTHER | [optional] |
| **primary_products** | **Array&lt;String&gt;** |  | [optional] |
| **target_audience** | **String** |  | [optional] |
| **brand_voice** | **String** |  | [optional] |
| **goals** | **String** |  | [optional] |
| **country_code** | **String** |  | [optional] |
| **language_code** | **String** |  | [optional] |
| **paused** | **Boolean** |  | [optional] |
| **google_play_id** | **String** |  | [optional] |
| **app_store_id** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **stats** | [**ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetails.new(
  id: null,
  name: null,
  brand_name: null,
  url: null,
  description: null,
  matching_names: null,
  industry: null,
  business_model: null,
  business_model_other: null,
  primary_products: null,
  target_audience: null,
  brand_voice: null,
  goals: null,
  country_code: null,
  language_code: null,
  paused: null,
  google_play_id: null,
  app_store_id: null,
  created_at: null,
  stats: null
)
```


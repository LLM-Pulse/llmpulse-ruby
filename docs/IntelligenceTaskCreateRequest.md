# LLMPulse::IntelligenceTaskCreateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **task_type** | **String** | product_listing is API-only: it needs product and returns ready-to-apply product page copy |  |
| **prompt_id** | **Integer** | Not used by product_listing; send null or omit it | [optional] |
| **custom_topic** | **String** |  | [optional] |
| **user_instructions** | **String** |  | [optional] |
| **output_language_code** | **String** |  | [optional] |
| **existing_content** | **String** |  | [optional] |
| **existing_content_url** | **String** |  | [optional] |
| **product** | [**IntelligenceTaskProduct**](IntelligenceTaskProduct.md) |  | [optional] |
| **prompt_ids** | **Array&lt;Integer&gt;** | product_listing only: up to 20 project prompts the copy should answer | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::IntelligenceTaskCreateRequest.new(
  project_id: null,
  task_type: null,
  prompt_id: null,
  custom_topic: null,
  user_instructions: null,
  output_language_code: null,
  existing_content: null,
  existing_content_url: null,
  product: null,
  prompt_ids: null
)
```


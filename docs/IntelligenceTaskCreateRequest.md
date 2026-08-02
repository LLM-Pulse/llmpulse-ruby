# LLMPulse::IntelligenceTaskCreateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **task_type** | **String** |  |  |
| **prompt_id** | **Integer** |  | [optional] |
| **custom_topic** | **String** |  | [optional] |
| **user_instructions** | **String** |  | [optional] |
| **output_language_code** | **String** |  | [optional] |
| **existing_content** | **String** |  | [optional] |
| **existing_content_url** | **String** |  | [optional] |

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
  existing_content_url: null
)
```


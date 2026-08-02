# LLMPulse::IntelligenceTask

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **public_id** | **String** |  | [optional] |
| **project_id** | **Integer** |  | [optional] |
| **task_type** | **String** |  | [optional] |
| **title** | **String** |  | [optional] |
| **status** | **String** |  | [optional] |
| **prompt_id** | **Integer** |  | [optional] |
| **prompt_text** | **String** |  | [optional] |
| **agentic_mode** | **Boolean** |  | [optional] |
| **custom_topic** | **String** |  | [optional] |
| **user_instructions** | **String** |  | [optional] |
| **output_language_code** | **String** |  | [optional] |
| **word_count** | **Integer** |  | [optional] |
| **result_data** | **Object** | Only present when status&#x3D;&#39;completed&#39; | [optional] |
| **error_message** | **String** |  | [optional] |
| **estimated_time** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **processed_at** | **Time** |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::IntelligenceTask.new(
  id: null,
  public_id: null,
  project_id: null,
  task_type: null,
  title: null,
  status: null,
  prompt_id: null,
  prompt_text: null,
  agentic_mode: null,
  custom_topic: null,
  user_instructions: null,
  output_language_code: null,
  word_count: null,
  result_data: null,
  error_message: null,
  estimated_time: null,
  created_at: null,
  processed_at: null,
  request_id: null
)
```


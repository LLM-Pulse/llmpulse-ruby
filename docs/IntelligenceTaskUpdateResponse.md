# LLMPulse::IntelligenceTaskUpdateResponse

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
| **manually_edited_at** | **Time** | When the content was last edited by hand; null while the output is as generated | [optional] |
| **edited_by_user_id** | **Integer** | User behind the last manual edit; null for an unedited task or an edit made from an embedded portal | [optional] |
| **request_id** | **String** |  | [optional] |
| **changed_paths** | **Array&lt;String&gt;** | Paths whose text actually changed; empty when every value matched the stored text | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::IntelligenceTaskUpdateResponse.new(
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
  manually_edited_at: null,
  edited_by_user_id: null,
  request_id: null,
  changed_paths: null
)
```


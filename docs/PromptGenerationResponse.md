# LLMPulse::PromptGenerationResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | The run id; poll GET /prompt_generations/{id} with it (kept for 24 hours) |  |
| **project_id** | **Integer** |  |  |
| **source** | **String** |  |  |
| **status** | **String** |  |  |
| **params** | [**PromptGenerationResponseParams**](PromptGenerationResponseParams.md) |  |  |
| **created_at** | **Time** |  |  |
| **finished_at** | **Time** |  |  |
| **suggestions_count** | **Integer** |  |  |
| **suggestions** | [**Array&lt;SuggestedPrompt&gt;**](SuggestedPrompt.md) | The suggestions the run saved to the Suggested prompts queue, with their current status |  |
| **error** | [**PromptGenerationResponseError**](PromptGenerationResponseError.md) |  |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PromptGenerationResponse.new(
  id: null,
  project_id: null,
  source: null,
  status: null,
  params: null,
  created_at: null,
  finished_at: null,
  suggestions_count: null,
  suggestions: null,
  error: null,
  request_id: null
)
```


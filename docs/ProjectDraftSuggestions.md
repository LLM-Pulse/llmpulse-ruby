# LLMPulse::ProjectDraftSuggestions

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **step** | **String** | The step the suggestions are for (details, prompts or competitors) | [optional] |
| **status** | **String** | ready, none (not requested, or nothing cached yet) or failed |  |
| **details** | [**ProjectDraftSuggestionsDetails**](ProjectDraftSuggestionsDetails.md) |  | [optional] |
| **prompts** | **Array&lt;String&gt;** |  | [optional] |
| **competitors** | [**Array&lt;ProjectDraftSuggestionsCompetitorsInner&gt;**](ProjectDraftSuggestionsCompetitorsInner.md) |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDraftSuggestions.new(
  step: null,
  status: null,
  details: null,
  prompts: null,
  competitors: null
)
```


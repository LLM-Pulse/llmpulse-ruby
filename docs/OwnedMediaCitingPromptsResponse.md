# LLMPulse::OwnedMediaCitingPromptsResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **provider** | **String** |  | [optional] |
| **from** | **Time** |  | [optional] |
| **to** | **Time** |  | [optional] |
| **item** | [**OwnedMediaCitedItem**](OwnedMediaCitedItem.md) |  | [optional] |
| **citation_count** | **Integer** | Citations of the item in the window | [optional] |
| **prompt_count** | **Integer** | Distinct prompts whose answers cited it | [optional] |
| **page** | **Integer** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **total** | **Integer** | Citing answers | [optional] |
| **data** | [**Array&lt;OwnedMediaCitingAnswer&gt;**](OwnedMediaCitingAnswer.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::OwnedMediaCitingPromptsResponse.new(
  project_id: null,
  provider: null,
  from: null,
  to: null,
  item: null,
  citation_count: null,
  prompt_count: null,
  page: null,
  per_page: null,
  total: null,
  data: null,
  request_id: null
)
```


# LLMPulse::PeecExportImportResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **import_id** | **Integer** |  |  |
| **status** | **String** | The import was accepted and finishes in the background |  |
| **prompts** | **Integer** | Distinct prompts of the file, per country and language; each becomes a tracked prompt of the project |  |
| **new_prompts** | **Integer** | The prompts the project does not hold yet, counted against the plan |  |
| **planned_answers** | **Integer** | Weekly answers the import files (prompts x tracked AI models x weeks) |  |
| **models** | **Hash&lt;String, String&gt;** | Each AI model name of the file that is imported, with the tracked AI model its answers are filed under |  |
| **skipped_models** | **Array&lt;String&gt;** | AI model names of the file whose answers are skipped, because the account does not track them |  |
| **detected_brands** | **Array&lt;String&gt;** | Brand names the export&#39;s mentions column lists (up to 50), none of them created as competitors |  |
| **app_url** | **String** | Opens the project&#39;s prompts in the app |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::PeecExportImportResponse.new(
  project_id: null,
  import_id: null,
  status: null,
  prompts: null,
  new_prompts: null,
  planned_answers: null,
  models: null,
  skipped_models: null,
  detected_brands: null,
  app_url: null,
  request_id: null
)
```


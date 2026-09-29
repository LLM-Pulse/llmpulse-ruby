# LLMPulse::LlmsTxtTechnicalGeoReportResultData

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **llms_txt_content** | **String** | Current llms.txt, manual edits included | [optional] |
| **llms_full_txt_content** | **String** | Current llms-full.txt, manual edits included | [optional] |
| **manually_edited_at** | **Time** | When the files were last edited by hand in the app, the API or MCP; null while they are as generated | [optional] |
| **content_version** | **String** | Send it back as content_version when editing the files. It changes on every save | [optional] |
| **original_llms_txt_content** | **String** | The generated llms.txt, kept from the first manual edit; null while the files are as generated | [optional] |
| **original_llms_full_txt_content** | **String** | The generated llms-full.txt, kept from the first manual edit; null while the files are as generated | [optional] |
| **crawl_data** | **Object** |  | [optional] |
| **metadata** | **Object** | Generation details, including output_language_code, the language the files were written in | [optional] |
| **pages_crawled** | **Integer** |  | [optional] |
| **generation_time_ms** | **Integer** |  | [optional] |
| **openai_tokens_used** | **Integer** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::LlmsTxtTechnicalGeoReportResultData.new(
  llms_txt_content: null,
  llms_full_txt_content: null,
  manually_edited_at: null,
  content_version: null,
  original_llms_txt_content: null,
  original_llms_full_txt_content: null,
  crawl_data: null,
  metadata: null,
  pages_crawled: null,
  generation_time_ms: null,
  openai_tokens_used: null
)
```


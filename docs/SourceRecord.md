# LLMPulse::SourceRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **prompt_execution_id** | **Integer** |  |  |
| **domain** | **String** | Registrable domain of the cited URL |  |
| **url** | **String** | Normalized cited URL (tracking parameters and fragment removed) |  |
| **url_sha256** | **String** | Key of the cited page, as GET /citation_intelligence/urls/{url_sha256} takes it |  |
| **position** | **Integer** | Rank of the citation in the answer; 0 for a background source reference with no visible rank |  |
| **source_type** | **String** | owned (the project&#39;s domains), competitor or third_party |  |
| **is_google_play_link** | **Boolean** |  |  |
| **is_app_store_link** | **Boolean** |  |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::SourceRecord.new(
  id: null,
  prompt_execution_id: null,
  domain: null,
  url: null,
  url_sha256: null,
  position: null,
  source_type: null,
  is_google_play_link: null,
  is_app_store_link: null,
  created_at: null
)
```


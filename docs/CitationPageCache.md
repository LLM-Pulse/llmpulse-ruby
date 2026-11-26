# LLMPulse::CitationPageCache

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **present** | **Boolean** | Whether the page has a saved copy |  |
| **last_crawled_at** | **Time** | When the saved copy was read; null without usable content |  |
| **status_code** | **Integer** | A saved successful response or an observed 404/410; null otherwise |  |
| **error_message** | **String** | Always null; crawl errors are not exposed |  |
| **content_format** | **String** |  |  |
| **bytes** | **Integer** |  |  |
| **html_title** | **String** |  |  |
| **meta_title** | **String** |  |  |
| **meta_description** | **String** |  |  |
| **h1** | **String** |  |  |
| **canonical_url** | **String** |  |  |
| **language** | **String** |  |  |
| **mentions_processed** | **Boolean** | Whether the page&#39;s mention analysis has completed for this project |  |
| **content_available** | **Boolean** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitationPageCache.new(
  present: null,
  last_crawled_at: null,
  status_code: null,
  error_message: null,
  content_format: null,
  bytes: null,
  html_title: null,
  meta_title: null,
  meta_description: null,
  h1: null,
  canonical_url: null,
  language: null,
  mentions_processed: null,
  content_available: null
)
```


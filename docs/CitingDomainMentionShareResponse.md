# LLMPulse::CitingDomainMentionShareResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  |  |
| **filters** | [**CitationIntelligenceFiltersEcho**](CitationIntelligenceFiltersEcho.md) |  |  |
| **normalization** | **String** | How the shares are computed |  |
| **data** | [**Array&lt;CitingDomainMentionShareResponseDataInner&gt;**](CitingDomainMentionShareResponseDataInner.md) | One row per requested domain (normalized, at most 50), in the order given |  |
| **request_id** | **String** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CitingDomainMentionShareResponse.new(
  project_id: null,
  filters: null,
  normalization: null,
  data: null,
  request_id: null
)
```


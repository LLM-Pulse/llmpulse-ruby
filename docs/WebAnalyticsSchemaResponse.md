# LLMPulse::WebAnalyticsSchemaResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **project_id** | **Integer** |  | [optional] |
| **provider** | **String** | The connected web analytics provider. | [optional] |
| **property** | **String** | The property, site, report suite (rsid:...), data view (dataview:...) or project every query runs on. | [optional] |
| **query_language** | **String** | The native query format the provider accepts. | [optional] |
| **docs_url** | **String** | The provider&#39;s reference for that format. | [optional] |
| **allowed_fields** | **Array&lt;String&gt;** | Top-level query fields that are forwarded. | [optional] |
| **rules** | **Array&lt;String&gt;** | What the bridge enforces and the provider&#39;s main constraints. | [optional] |
| **example** | **Hash&lt;String, Object&gt;** | A worked query to adapt. | [optional] |
| **fields** | **Hash&lt;String, Object&gt;** | The provider&#39;s live field list where it offers one: GA4 dimensions and metrics with custom definitions, Adobe ids, Matomo report methods, PostHog event names, the Plausible catalog. Null when the provider did not return it. | [optional] |
| **fields_unavailable** | **String** | Present when the field list could not be read; the format and example still apply. | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::WebAnalyticsSchemaResponse.new(
  project_id: null,
  provider: null,
  property: null,
  query_language: null,
  docs_url: null,
  allowed_fields: null,
  rules: null,
  example: null,
  fields: null,
  fields_unavailable: null,
  request_id: null
)
```


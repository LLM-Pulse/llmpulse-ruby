# LLMPulse::ProjectProfile

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  |  |
| **name** | **String** |  |  |
| **brand_name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **industry** | **Object** | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings. Deliberately untyped so generated clients decode either shape | [optional] |
| **business_model** | **String** |  | [optional] |
| **business_model_other** | **String** | Set only when business_model is OTHER | [optional] |
| **target_audience** | **String** |  | [optional] |
| **primary_products** | **Array&lt;String&gt;** |  | [optional] |
| **brand_voice** | **String** |  | [optional] |
| **goals** | **String** |  | [optional] |
| **matching_names** | **Array&lt;String&gt;** |  |  |
| **additional_owned_domains** | **Array&lt;String&gt;** | Other domains the brand owns (at most 10, each a website&#39;s own domain covering its subdomains), whose citations count as owned like the project website. Empty when none |  |
| **prompt_limit** | **Integer** | The most prompts this project can hold, set by the account owner or a co-owner (Account Settings &gt; Prompt Limits). Null when the project has no limit of its own; the account&#39;s plan allowance applies either way |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectProfile.new(
  id: null,
  name: null,
  brand_name: null,
  description: null,
  industry: null,
  business_model: null,
  business_model_other: null,
  target_audience: null,
  primary_products: null,
  brand_voice: null,
  goals: null,
  matching_names: null,
  additional_owned_domains: null,
  prompt_limit: null
)
```


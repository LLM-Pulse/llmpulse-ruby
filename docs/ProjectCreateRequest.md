# LLMPulse::ProjectCreateRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **website_url** | **String** | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. |  |
| **name** | **String** |  |  |
| **main_country** | **String** |  |  |
| **main_language** | **String** |  |  |
| **brand_name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **industry** | **Array&lt;String&gt;** |  | [optional] |
| **business_model** | **String** | Business model key (e.g. B2B_SAAS, MARKETPLACE); unknown keys are rejected | [optional] |
| **business_model_other** | **String** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key | [optional] |
| **target_audience** | **String** | Who the brand sells to. Context for Recommendations and GEO Writer (Brand Book) | [optional] |
| **brand_voice** | **String** | Tone of voice guidance for generated content (Brand Book) | [optional] |
| **goals** | **String** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions | [optional] |
| **primary_products** | **Array&lt;String&gt;** | Main products or services | [optional] |
| **matching_names** | **Array&lt;String&gt;** |  | [optional] |
| **prompts** | **Array&lt;String&gt;** |  | [optional] |
| **competitors** | [**Array&lt;ProjectCreateRequestCompetitorsInner&gt;**](ProjectCreateRequestCompetitorsInner.md) |  | [optional] |
| **owned_media** | [**ProjectCreateRequestOwnedMedia**](ProjectCreateRequestOwnedMedia.md) |  | [optional] |
| **use_subdomain** | **Boolean** |  | [optional][default to false] |
| **weekly_email_subscribed** | **Boolean** |  | [optional][default to false] |
| **external_identifier** | **String** | Embed-enabled (Enterprise) accounts only; other accounts receive ERR_PLAN_REQUIRED. Idempotency key and embed-session join key, unique per account | [optional] |
| **execute_prompts_immediately** | **Boolean** |  | [optional][default to true] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectCreateRequest.new(
  website_url: https://acme.com,
  name: Acme,
  main_country: US,
  main_language: en,
  brand_name: null,
  description: null,
  industry: [&quot;SAAS&quot;],
  business_model: B2B_SAAS,
  business_model_other: null,
  target_audience: null,
  brand_voice: null,
  goals: null,
  primary_products: null,
  matching_names: null,
  prompts: null,
  competitors: null,
  owned_media: null,
  use_subdomain: null,
  weekly_email_subscribed: null,
  external_identifier: null,
  execute_prompts_immediately: null
)
```


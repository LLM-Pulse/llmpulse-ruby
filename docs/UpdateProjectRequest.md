# LLMPulse::UpdateProjectRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **brand_name** | **String** | Brand name used to detect mentions. Applies to future runs; it does not rewrite history | [optional] |
| **description** | **String** | What the brand does. Context for Recommendations and GEO Writer (Brand Book) | [optional] |
| **industry** | **String** | Single industry key (e.g. SAAS); unknown keys are rejected | [optional] |
| **business_model** | **String** | Business model key (e.g. B2B_SAAS); unknown keys are rejected | [optional] |
| **business_model_other** | **String** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key | [optional] |
| **target_audience** | **String** | Who the brand sells to (Brand Book) | [optional] |
| **brand_voice** | **String** | Tone of voice guidance for generated content (Brand Book) | [optional] |
| **goals** | **String** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions | [optional] |
| **primary_products** | **Array&lt;String&gt;** | Full replacement list of the main products or services | [optional] |
| **matching_names** | **Array&lt;String&gt;** | FULL replacement list of the brand-name variants used to detect mentions; send every variant to keep | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::UpdateProjectRequest.new(
  brand_name: null,
  description: null,
  industry: null,
  business_model: null,
  business_model_other: null,
  target_audience: null,
  brand_voice: null,
  goals: null,
  primary_products: null,
  matching_names: null
)
```


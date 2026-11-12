# LLMPulse::ProjectDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **name** | **String** | Internal project label (sidebar, settings, admin) | [optional] |
| **brand_name** | **String** | LLM-facing brand label (used in prompts and customer-facing charts). Null when not set, in which case prompts and charts use &#x60;name&#x60;. | [optional] |
| **tracked** | **Boolean** | Whether scheduled runs include this project. False when it is a pitch project, which runs once, when it is paused, or when the plan&#39;s project limit leaves it out (the oldest projects up to the limit run), so its prompts do not run |  |
| **untracked_reason** | **String** | Why tracked is false: pitch_project, paused or project_limit. Null when tracked |  |
| **pitch** | **Boolean** | Whether this is a pitch project, a one-off snapshot that runs its prompts once, takes no project slot and is deleted at pitch_expires_at unless it is converted (PATCH /projects/{id} with pitch false) | [optional] |
| **pitch_expires_at** | **Time** | When a pitch project is deleted, with its data, unless it is converted first. Null for a tracked project | [optional] |
| **url** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **matching_names** | **Array&lt;String&gt;** |  | [optional] |
| **additional_owned_domains** | **Array&lt;String&gt;** | Other domains the brand owns (at most 10, each a website&#39;s own domain covering its subdomains), whose citations count as owned like the project website. Empty when none | [optional] |
| **industry** | **Object** | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings when the project was created with a list or the in-app multi-select. Deliberately untyped so generated clients decode either shape | [optional] |
| **business_model** | **String** |  | [optional] |
| **business_model_other** | **String** | Set only when business_model is OTHER | [optional] |
| **primary_products** | **Array&lt;String&gt;** |  | [optional] |
| **target_audience** | **String** |  | [optional] |
| **brand_voice** | **String** |  | [optional] |
| **goals** | **String** |  | [optional] |
| **country_code** | **String** |  | [optional] |
| **language_code** | **String** |  | [optional] |
| **paused** | **Boolean** |  | [optional] |
| **google_play_id** | **String** |  | [optional] |
| **app_store_id** | **String** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **prompt_limit** | **Integer** | The most prompts this project can hold, set by the account owner or a co-owner (Account Settings &gt; Prompt Limits). Null when the project has no limit of its own; the account&#39;s plan allowance applies either way | [optional] |
| **project_type** | **String** | The project type it is billed as under the account&#39;s pricing agreement, such as core or lean (its own, else the account&#39;s default type). Null for accounts without per-project types and for pitch projects | [optional] |
| **stats** | [**ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md) |  | [optional] |
| **pitch_run** | [**ProjectDetailsAllOfPitchRun**](ProjectDetailsAllOfPitchRun.md) |  | [optional] |
| **data_coverage** | [**ProjectDetailsAllOfDataCoverage**](ProjectDetailsAllOfDataCoverage.md) |  | [optional] |
| **search_console** | [**ProjectDetailsAllOfSearchConsole**](ProjectDetailsAllOfSearchConsole.md) |  | [optional] |
| **ai_traffic** | [**ProjectDetailsAllOfAiTraffic**](ProjectDetailsAllOfAiTraffic.md) |  | [optional] |
| **agent_traffic** | [**ProjectDetailsAllOfAgentTraffic**](ProjectDetailsAllOfAgentTraffic.md) |  | [optional] |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDetails.new(
  id: null,
  name: null,
  brand_name: null,
  tracked: null,
  untracked_reason: null,
  pitch: null,
  pitch_expires_at: null,
  url: null,
  description: null,
  matching_names: null,
  additional_owned_domains: null,
  industry: null,
  business_model: null,
  business_model_other: null,
  primary_products: null,
  target_audience: null,
  brand_voice: null,
  goals: null,
  country_code: null,
  language_code: null,
  paused: null,
  google_play_id: null,
  app_store_id: null,
  created_at: null,
  prompt_limit: null,
  project_type: null,
  stats: null,
  pitch_run: null,
  data_coverage: null,
  search_console: null,
  ai_traffic: null,
  agent_traffic: null,
  request_id: null
)
```


# LLMPulse::ProjectDraftRecord

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **draft_id** | **String** | Draft id (draft_...) |  |
| **status** | **String** | open, finalized or expired |  |
| **current_step** | **String** | The next step to submit (details, prompts, competitors, owned_media), or ready when the draft can be finalized |  |
| **steps_completed** | **Array&lt;String&gt;** |  |  |
| **steps_remaining** | **Array&lt;String&gt;** | Required steps not submitted yet |  |
| **optional_steps** | **Array&lt;String&gt;** | Steps the plan allows but finalize does not require (owned_media from Growth) |  |
| **finalizable** | **Boolean** |  |  |
| **website_url** | **String** |  |  |
| **main_country** | **String** |  |  |
| **main_language** | **String** |  |  |
| **use_subdomain** | **Boolean** |  |  |
| **name** | **String** | Null until the details step |  |
| **brand_name** | **String** |  |  |
| **description** | **String** |  |  |
| **industry** | **Array&lt;String&gt;** |  |  |
| **matching_names** | **Array&lt;String&gt;** |  |  |
| **prompts** | **Array&lt;String&gt;** |  |  |
| **competitors** | [**Array&lt;ProjectDraftRecordCompetitorsInner&gt;**](ProjectDraftRecordCompetitorsInner.md) |  |  |
| **owned_media** | [**ProjectDraftRecordOwnedMedia**](ProjectDraftRecordOwnedMedia.md) |  |  |
| **weekly_email_subscribed** | **Boolean** |  |  |
| **external_identifier** | **String** |  |  |
| **execute_prompts_immediately** | **Boolean** |  |  |
| **project_id** | **Integer** | The project the draft became; null until finalized |  |
| **expires_at** | **Time** |  |  |
| **created_at** | **Time** |  |  |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::ProjectDraftRecord.new(
  draft_id: null,
  status: null,
  current_step: null,
  steps_completed: null,
  steps_remaining: null,
  optional_steps: null,
  finalizable: null,
  website_url: null,
  main_country: null,
  main_language: null,
  use_subdomain: null,
  name: null,
  brand_name: null,
  description: null,
  industry: null,
  matching_names: null,
  prompts: null,
  competitors: null,
  owned_media: null,
  weekly_email_subscribed: null,
  external_identifier: null,
  execute_prompts_immediately: null,
  project_id: null,
  expires_at: null,
  created_at: null
)
```


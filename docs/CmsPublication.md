# LLMPulse::CmsPublication

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** |  | [optional] |
| **platform** | **String** |  | [optional] |
| **site_url** | **String** |  | [optional] |
| **status** | **String** | queued and sending are on their way; unknown means a send timed out and the next attempt looks the draft up before creating one; drafted carries remote_id and edit_url; failed carries error_code | [optional] |
| **title** | **String** |  | [optional] |
| **slug** | **String** |  | [optional] |
| **source_url** | **String** | For an update task, the page the draft revises | [optional] |
| **remote_id** | **Integer** | WordPress post id of the draft | [optional] |
| **remote_status** | **String** | WordPress status of the post when the draft was created (draft) | [optional] |
| **remote_url** | **String** |  | [optional] |
| **edit_url** | **String** | The post&#39;s edit screen in the WordPress admin | [optional] |
| **error_code** | **String** | Why the send failed, for example reconnect_required, missing_capability, unreachable or rejected | [optional] |
| **created_at** | **Time** |  | [optional] |
| **sent_at** | **Time** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CmsPublication.new(
  id: null,
  platform: null,
  site_url: null,
  status: null,
  title: null,
  slug: null,
  source_url: null,
  remote_id: null,
  remote_status: null,
  remote_url: null,
  edit_url: null,
  error_code: null,
  created_at: null,
  sent_at: null
)
```


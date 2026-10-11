# LLMPulse::CreateTeamInvitation201Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **Integer** | Kept by the member once they accept, when they move to GET /team_members. |  |
| **email** | **String** |  |  |
| **permission_role** | **String** |  |  |
| **account_role** | [**TeamAccountRole**](TeamAccountRole.md) |  |  |
| **permissions** | **Hash&lt;String, Array&lt;String&gt;&gt;** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. |  |
| **account_admin** | **Boolean** |  |  |
| **billing_access** | **Boolean** |  |  |
| **all_projects** | **Boolean** |  |  |
| **project_ids** | **Array&lt;Integer&gt;** |  |  |
| **invited_at** | **Time** | When the invitation email was last sent. | [optional] |
| **expires_at** | **Time** | When the invitation link stops working. | [optional] |
| **created_at** | **Time** |  | [optional] |
| **email_sent** | **Boolean** | False when the email provider refused the invitation email |  |
| **request_id** | **String** |  | [optional] |

## Example

```ruby
require 'llmpulse'

instance = LLMPulse::CreateTeamInvitation201Response.new(
  id: null,
  email: null,
  permission_role: null,
  account_role: null,
  permissions: null,
  account_admin: null,
  billing_access: null,
  all_projects: null,
  project_ids: null,
  invited_at: null,
  expires_at: null,
  created_at: null,
  email_sent: null,
  request_id: null
)
```

